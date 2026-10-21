# Chapter 3: The Bookstore in the Garage and the Escrow by the Lake

Summer 1994. The sweltering heat of Manhattan wrapped around everyone like a wet cloth.

Jeff Bezos sat in the office of a hedge fund company, a report displayed on his computer screen: Internet annual growth rate of 2,300%. He was 30 years old, a Princeton graduate who had worked on Wall Street for several years. The job was respectable and paid well, but Bezos always felt something was missing.

That report struck him like lightning.

"If the internet is growing at this speed," he calculated in his mind, "in a few years, it will change everything."

He listed 20 types of products that could be sold online and finally chose books—standardized, easy to ship, massive SKU. There were 3 million books in the world; no physical bookstore could stock them all, but an online bookstore could.

Bezos decided to quit his job and start a business.

His wife MacKenzie sat in the passenger seat while he wrote the business plan on his lap. They drove from New York across the United States, their destination Seattle—a city closer to book distribution centers and more tax-friendly.

In July 1994, Bezos rented a garage in the suburbs of Seattle. The garage was small, fitting only a few folding tables and a computer. He named it Cadabra, then changed it to Amazon—the largest river in the world. He would build the world's largest bookstore.

On July 16, 1995, Amazon went live.

That morning, Bezos sat at the folding table in the garage, eyes fixed on the order system on the screen. He had listed 1 million books but didn't know if anyone would buy them.

The first order came in.

A copy of Douglas Hofstadter's *Fluid Concepts and Creative Analogies*, shipped to Seattle customer John Wainwright. Bezos packed it himself, wrapped it in bubble wrap, stuck on the address label, then drove to the post office to send it.

He stood at the post office counter, watching the clerk put the package into a bag, a strange feeling welling up inside—he was doing something that might change the world.

Within 30 days of launch, Amazon sold books to 50 states and 45 countries.

---

**Meanwhile, on the other side of the Earth.**

Spring 1999. Hangzhou.

Room 801, Building 16, Lakeside Gardens—a ordinary residential apartment. Five tables were set up in the living room, boxes of instant noodles stacked in the corner, the air thick with the smell of cheap cigarettes and instant noodles.

35-year-old Jack Ma stood in the center of the living room, facing 16 young people—his "Eighteen Arhats" (including Jack Ma and his wife themselves).

Jack Ma waved his arms, his voice hoarse with excitement: "We are going to build a company that survives for 102 years! We will become the world's largest e-commerce company!"

The 16 young people looked at him. Some were excited, some doubtful, some just needed a job.

Sun Tongyu quietly asked Peng Lei beside him: "Do you think he can succeed?"

Peng Lei smiled: "I don't know, but at least it's more interesting than our previous jobs."

Alibaba initially adopted a B2B model—"China Suppliers," helping Chinese factories find overseas buyers. But Jack Ma soon discovered a bigger opportunity: Chinese consumers also needed to buy things online.

Why weren't Chinese people shopping online?

**No trust.** Buyers worried: What if I pay and the seller doesn't ship? Sellers worried: What if I ship and the buyer doesn't pay?

Transaction parties were separated by screens, with information asymmetry—buyers didn't know if sellers were trustworthy; sellers didn't know if buyers had money. Offline, face-to-face transactions could be resolved through observation, negotiation, and third-party guarantees. But online, this information gap was magnified.

Jack Ma's solution was: start with B2B, let factories and wholesalers build trust; then do C2C (Taobao), let individual sellers and individual buyers trade; finally do B2C (Tmall), let brands sell directly to consumers.

In 2003, Taobao was founded.

At that time, eBay had entered China through the acquisition of EachNet, occupying 90% of the C2C market. Jack Ma's opponent was the world's largest e-commerce platform.

But what he didn't know was that on the other side of the Pacific, a bigger opponent was rising—Amazon.

And Taobao would use a completely different path to defeat eBay and challenge Amazon.

The war of code had entered a new battlefield.

---

In May 2003, shortly after Taobao launched.

Programmer Duolong stared at the database error on the screen, frowning. User volume had exceeded expectations, but the MySQL database was starting to struggle.

"Order table query timeout," Duolong said to a colleague beside him. "We need to optimize."

"How?" the colleague asked.

"Sharding," Duolong said. "Scatter orders into different tables based on user ID. When querying, first locate the specific table."

This was the origin of database sharding. When data volume exceeds the capacity of a single table, distribute data across multiple tables to reduce pressure on any single table.

---

The essence of e-commerce is the transaction system. Buyer pays, seller ships, platform takes commission. Seems simple, but it's actually an extremely complex distributed system.

Each product has an SKU (Stock Keeping Unit), containing attributes like name, description, price, inventory, and images. When there are only a few thousand products, Excel can manage them. But when products reach tens of millions, a database is needed.

Amazon used Oracle databases in its early days. Oracle is powerful, supporting transactions, indexes, and stored procedures, but it has one problem: **expensive**. Oracle charges by CPU core; a single server could cost hundreds of thousands of dollars. Every additional server means linear cost growth.

Taobao started with PHP and MySQL. MySQL is open-source and free—no matter how many servers you deploy, there are no additional licensing fees.

As traffic grew, Taobao gradually adopted Java and Oracle, deeply customizing database sharding, read-write separation, and caching layers.

Product search is another challenge. Traditional database LIKE queries are too inefficient to support fuzzy searches.

Amazon developed its own search engine A9 in 2003. Taobao developed Ha3 in 2008, supporting hundred-million-level product searches.

The core of search is the inverted index. Each keyword corresponds to a list of products; when searching, the system merges inverted lists from multiple keywords—far faster than scanning the entire catalog, with cost driven by list lengths.

For example: 10 million products, searching for "iPhone 15." In the inverted index, "iPhone" corresponds to 1 million items, "15" corresponds to 500,000 items. The system takes the intersection, finding 100,000 matching products in milliseconds.

Without this technology, e-commerce search would be impossible.

---

The shopping cart is the core function of e-commerce. Users browse products, add them to the cart, and finally settle together.

Where is the state stored?

**Option 1: Client-side storage**. Using cookies or localStorage. Advantage: no server pressure. Disadvantage: cart is lost when switching devices.

**Option 2: Server-side storage**. Using database or cache. Advantage: cross-device synchronization. Disadvantage: server pressure.

Amazon uses Option 2. Taobao also uses Option 2, but with an innovation: shopping cart data is first written to Redis cache, then asynchronously written to the database.

Redis is an in-memory database, with read-write speeds 100 times faster than disk. Users hardly feel any delay, and database pressure is greatly reduced.

---

After the user clicks "place order," a series of operations occur: creating an order record, deducting inventory, generating a payment order, sending notifications.

These operations must all succeed or all fail. If the order succeeds but inventory deduction fails, you get overselling—users bought the product, but the warehouse has no stock.

Database transactions guarantee ACID properties: Atomicity, Consistency, Isolation, Durability.

Taobao used two-phase commit protocols in its early days. The coordinator first sends a "prepare" request; participants lock resources and return "ready." Then the coordinator sends a "commit" request, and participants complete the operation.

But two-phase commit has a problem: if the coordinator crashes, participants will keep resources locked, causing system blockage.

Later, Taobao developed the TCC pattern: Try (reserve resources), Confirm (confirm operation), Cancel (cancel operation). If Confirm fails, execute Cancel to roll back.

The advantage of TCC is that it doesn't require global locks; the system can process concurrently. But business logic is complex, requiring three sets of code for each operation.

---

The scenario that most tests e-commerce technology is flash sales.

Suppose there are 100 items in stock, and 100,000 users are rushing to buy simultaneously. If you simply deduct inventory, overselling occurs: 100 items are sold to 1,000 users.

The solution is distributed locks. When a user clicks "buy," the system first acquires a lock for that product. If successful, deduct inventory and release the lock; if failed, return "sold out."

Taobao uses Redis to implement distributed locks. A command such as `SET key value NX EX 10` can atomically acquire a lock with expiry:

```
SET lock:iphone15 1 NX EX 10  // Set lock, automatically expires after 10 seconds
```

If it returns 1, lock acquisition succeeded; returns 0, lock is already held.

But distributed locks also have a problem: with 100,000 users competing for 100 items, 99.9% of users will fail to acquire the lock. The system needs to quickly return "sold out" rather than making users wait.

Taobao's solution is the token bucket: the system pre-generates 100 tokens; users grab tokens when rushing to buy. When tokens are exhausted, subsequent users directly return "sold out" without trying to acquire the lock.

This greatly reduces system pressure.

---

Payment is the hardest part of e-commerce.

In the 1990s US, credit cards were already widespread. Users enter card number, expiration date, and CVV code to complete payment. Banks process authorization; merchants receive funds.

But in China, credit cards weren't widespread; most people used cash or bank transfers. Online payment hardly existed.

Users worried: What if I pay and the merchant doesn't ship? Merchants worried: What if I ship and the buyer doesn't pay?

eBay used PayPal to solve this problem in the US. PayPal acts as an intermediary: buyer pays PayPal, PayPal holds the funds; after buyer confirms receipt, PayPal pays the seller.

Taobao's solution was Alipay.

In October 2003, Alipay went live. Buyers pay to Alipay; Alipay notifies the seller to ship; after buyer confirms receipt, Alipay pays the seller.

But Alipay had a challenge that PayPal didn't: Chinese banking systems didn't support online payments.

The Alipay team had to negotiate with banks one by one to access their gateways. Users place orders on Alipay, jump to the bank's online banking page to complete payment, then jump back to Alipay. This process was cumbersome, but it was the only feasible way at the time.

In 2004, Alipay connected to its first bank—ICBC. By 2008, it had connected to almost all mainstream banks.

Alipay's success solved the trust problem for Chinese e-commerce. Users began to dare to shop online; merchants began to dare to open online stores.

**Trust finally had a digital carrier.**

---

In 2003, in Hangzhou.

Jack Ma sat in his office, the report in front of him making him frown. eBay had entered China through the acquisition of EachNet, occupying 90% of the C2C market share. Taobao had just launched with few users.

"How do we fight?" someone asked.

Jack Ma was silent for a moment, then said: "Free."

"eBay charges store fees, transaction fees, and advertising fees. We don't charge. Sellers come to Taobao to open stores, completely free."

"Then how do we make money?"

"We don't for now," Jack Ma said. "We'll figure it out when we have more users."

---

This was a difficult decision.

Taobao had no revenue, only expenses. Servers, bandwidth, staff salaries—burning money every month. Alibaba's B2B business made money, but it was all subsidizing Taobao.

Jack Ma knew that in a world where platforms connect buyers and sellers, user volume is the foundation of everything. More buyers mean more sellers willing to join; more sellers mean richer products, which means more buyers.

This mutually reinforcing relationship is the essential characteristic of the internet economy—**network effects**: product value grows exponentially with the number of users.

eBay charged fees; Taobao was free. Price-sensitive small and medium sellers migrated from eBay to Taobao one after another.

In 2005, Taobao's market share exceeded eBay's. In 2006, eBay withdrew from the Chinese market.

Free is not a business model; free is a means of acquiring users. When user scale reaches a critical point, network effects begin to manifest, and platform value grows exponentially.

---

Amazon and Taobao represent two e-commerce models.

Amazon initially used a self-operated model. It purchased products itself, stored them itself, sold them itself, and delivered them itself. What users bought came from Amazon, not third-party sellers.

The advantage of self-operation is quality control. Amazon selects suppliers, guarantees product quality, and can control logistics speed.

The disadvantage of self-operation is limited categories. Amazon couldn't possibly sell everything itself. Books and electronics could be self-operated, but clothing, furniture, and long-tail products were difficult to self-operate.

In 2000, Amazon began opening its platform, allowing third-party sellers to open stores on Amazon.

This was a key decision. Amazon discovered that when platforms connect enough buyers and sellers, a self-reinforcing cycle emerges—the **self-reinforcing cycle of network effects**: cost advantages brought by scale expansion translate into lower prices, attracting more users, which in turn attracts more sellers.

- More sellers join → Richer products
- Richer products → More buyers
- More buyers → More sellers (cycle)

By 2020, third-party seller sales accounted for more than 60% of Amazon's total sales.

But Amazon's platform has a controversial point: self-operation competes with third parties. Amazon both self-operates products and allows third-party sellers to sell the same products. This raises fairness issues: Does Amazon use platform data to suppress third-party sellers?

---

Taobao was a pure platform model from the start. Taobao doesn't sell goods itself; it only provides a trading platform. Anyone can open a store on Taobao and sell anything.

The advantage of the platform model is unlimited categories. There are billions of products on Taobao—from iPhones to coffins, from airplanes to pets, everything imaginable.

The disadvantage of the platform model is difficult quality control. Counterfeit goods, inferior products, and fraudulent behavior abound. Taobao was once called "counterfeit heaven."

Jack Ma's response was: Taobao is just a marketplace, like offline wholesale markets. Market managers don't guarantee product quality; buyers need to judge for themselves.

This response was acceptable in the early days. But as Taobao's scale expanded, the counterfeit problem became increasingly serious, affecting its reputation.

In 2008, Taobao launched "Taobao Mall," only allowing brand merchants to join; in 2012 the business was renamed "Tmall." Tmall has strict qualification reviews for merchants and quality guarantees for products. Tmall charges higher commissions but provides better user experience.

The division of labor between Taobao and Tmall gradually became clear: Taobao is the bazaar—cheap, rich, and mixed; Tmall is the mall—authentic, quality, and higher priced.

This is the **price structure design of platforms connecting users and services**: providing low-price services to price-sensitive users (bazaar sellers) and high-price services to quality-sensitive users (brand sellers).

---

Before the rise of Amazon and Taobao, the pioneer of e-commerce was eBay.

eBay was founded in 1995, a few months after Amazon. Founder Pierre Omidyar initially wanted to create an online auction platform.

Auctions are suitable for unique, scarce, and price-uncertain goods: collectibles, art, second-hand items.

But auctions aren't suitable for standardized, mass-selling goods: iPhones, laundry detergent, tissues—these things don't need auctions; direct pricing is more convenient.

eBay was the world's largest e-commerce platform in the early 2000s. But the auction model limited growth. Users didn't want to wait several days for an auction to end every time they bought something; they wanted to buy immediately.

Amazon seized this opportunity, launching the "1-Click" feature. After users saved payment and shipping information, they could complete purchases with a single button click. This feature greatly improved conversion rates.

eBay later launched the "Buy It Now" feature, but it was too late.

By 2020, Amazon's market cap was $1.5 trillion; eBay's was $30 billion. A 50-fold gap.

This 50-fold gap comes from the power of the **self-reinforcing cycle of network effects**: the larger the scale, the lower logistics and procurement costs, which can be converted into price advantages, then into user advantages.

Amazon used a hybrid model of self-operation + platform to convert cost advantages brought by scale expansion into price advantages, then into user advantages.

This is the secret of platform-based e-commerce.

---

The prosperity of e-commerce cannot be separated from underlying infrastructure.

E-commerce needs servers. Servers need data centers.

Data centers are huge buildings with thousands of servers arranged inside. Air conditioning maintains constant temperature (22°C±2), UPS and diesel generators ensure uninterrupted power supply, and network systems connect to the external internet.

In the 1990s, companies usually built their own data centers. Amazon built its own data center in 2000 to support its e-commerce business.

But building data centers is costly. You need to buy land, build buildings, buy equipment, and hire maintenance staff. And capacity is hard to predict: Double 11 traffic is ten times normal, so you need to prepare servers for peak times, but these servers are idle at normal times.

This is the problem of investment recovery. Investment in data centers is one-time and cannot be recovered. If business growth falls short of expectations, this investment is wasted.

Amazon's engineers came up with an idea: rent out idle servers.

In 2006, Amazon launched AWS (Amazon Web Services). Initially, there were only three services: S3 (object storage), EC2 (virtual servers), and SQS (message queue). Any company could rent servers on AWS, paying by usage.

AWS pioneered the cloud computing era. Startups no longer needed to build their own data centers; they could simply register on AWS and launch servers within minutes.

**The cost of serving each additional user approaches zero**: AWS's fixed cost of deploying a server is high, but the cost of serving each additional user is almost zero.

Taobao also experienced the transition from self-built data centers to cloud computing. In 2009, Alibaba established Alibaba Cloud, transforming Taobao's IT infrastructure into cloud services. Later, Alibaba Cloud became China's largest cloud computing company.

---

The core of e-commerce is transactions; the core of transactions is databases.

In the 1990s, Oracle was the king of the database market. Supporting ACID transactions, high availability, and distributed deployment, it was the first choice for enterprise applications.

Amazon used Oracle in its early days. Taobao also used Oracle in its early days.

But Oracle has one problem: it's expensive. Charged by CPU core, a single server could cost hundreds of thousands of dollars. And Oracle is closed-source; you cannot modify the source code.

For Taobao, this was a dependency risk. If they continued to rely on Oracle, development would be limited by licensing fees. More frighteningly, Oracle could raise prices at any time; Taobao had no bargaining power.

Taobao began the "De-IOE" campaign in 2008: replacing Oracle with MySQL, replacing IBM minicomputers with PC servers, and replacing EMC storage with self-developed storage.

This was a difficult decision. MySQL's functionality wasn't as good as Oracle's; the Taobao team had to develop numerous patches and middleware to support traffic.

But this decision freed Taobao from dependence on Oracle, saving huge costs. More importantly, Taobao accumulated a self-controllable technology stack, which later became the core competitiveness of Alibaba Cloud.

Amazon went through a similar process. They developed Dynamo, a distributed key-value storage system for supporting high-concurrency scenarios like shopping carts. Dynamo later evolved into AWS's DynamoDB service.

**The choice of database determines the cost and flexibility of e-commerce platforms.**

---

E-commerce websites have massive static resources: product images, CSS styles, JavaScript code. These resources need to be transmitted from servers to user browsers.

If the user is in China and the server is in the US, image transmission needs to cross the Pacific, with latency possibly reaching hundreds of milliseconds. For web loading, this is unacceptable.

CDN (Content Delivery Network) solves this problem. CDNs deploy hundreds of nodes globally, with each node caching website static resources. When users access, they get resources from the nearest node, greatly reducing latency.

Amazon launched CloudFront in 2008, AWS's CDN service. Taobao uses Alibaba Cloud CDN, with more than 2,000 nodes in China.

CDN not only accelerates web loading but also reduces origin server pressure. Most requests are handled by CDN nodes; only a few need to go back to the origin.

This is the manifestation of **cost advantages brought by scale expansion**: CDN service providers deploy global nodes with huge fixed costs, but the cost of serving each additional user is extremely low.

---

Another major challenge for e-commerce is logistics.

In its early days, Amazon didn't deliver itself, relying on third-party logistics like UPS and FedEx. But Bezos quickly realized that logistics is key to user experience. If delivery is too slow, users won't come back.

Amazon began building its own logistics network: warehouses, sorting centers, delivery stations. By 2020, Amazon had more than 400,000 delivery employees, becoming one of the world's largest logistics companies.

This is a cost decision. The upfront investment in self-built logistics is huge (buying land, building warehouses, buying vehicles, hiring people), and the cost of serving each additional user is positive. But as scale expands, unit logistics costs decrease. When order volume reaches a certain scale, self-built logistics is cheaper than third-party.

Taobao chose a different path. Taobao is a platform; it doesn't sell goods itself or deliver itself. Logistics are handled by sellers themselves.

This leads to uneven logistics quality. Some sellers use SF Express, delivering in two days; some sellers use regular mail, taking two weeks. User experience cannot be guaranteed.

In 2013, Alibaba partnered with multiple logistics companies to establish Cainiao Network. Cainiao doesn't deliver directly but builds a logistics information platform: courier companies connect to the Cainiao system, uploading package locations in real-time; users can check logistics progress on Taobao.

Cainiao also builds warehouse networks. Sellers can store goods in Cainiao warehouses, with Cainiao handling unified shipping. This way, sellers don't need to rent warehouses or hire workers themselves, reducing operating costs.

Cainiao's model is a platform connecting sellers and logistics companies: more sellers mean logistics companies are more willing to connect; more logistics companies mean more complete services, which means more sellers are willing to use it.

This is the **mutually reinforcing relationship of platforms connecting two-sided users**—**network effects**: product value grows exponentially with the number of users.

---

In 2009, Alibaba established Alibaba Cloud.

Jack Ma said at an internal meeting: "We want to build China's AWS."

Someone questioned: "Can Alibaba Cloud make money?"

Jack Ma replied: "Not now, but it will in the future. When all enterprises are running in the cloud, Alibaba Cloud will be infrastructure, just like power companies."

Ten years later, Alibaba Cloud's annual revenue exceeded 60 billion RMB.

**Software defines experience; hardware defines boundaries.**

The magic of e-commerce is the product of code running on silicon.

---

Autumn 2005. I bought something on Taobao for the first time.

It was an out-of-print computer textbook, no longer available in the market, but someone was selling it on Taobao. The book price was 35 yuan, shipping 5 yuan, total 40 yuan.

After placing the order, I transferred money to Alipay, then stared at the logistics information for five whole days. Refreshed dozens of times every day, watching the package ship from Hangzhou to Beijing. Status changed from "shipped" to "in transit" to "out for delivery."

When the courier knocked, I almost ran to open the door.

The package was small, just an ordinary courier bag. I opened it; the book lay quietly inside, cover somewhat worn but pages intact.

Confirm receipt, Alipay releases funds—the whole process complete, and only then did I truly believe: you really can do business with strangers online.

That moment, I understood the power of trust.

Offline, I could see the seller's shop, touch the product, and bargain with the seller. Online, I couldn't see anything; I could only trust Alipay's guarantee.

Alipay builds a **bridge of trust between buyers and sellers**—buyers dare to pay because money is in Alipay's hands; sellers dare to ship because buyers have already paid.

**Trust is the currency of e-commerce. Without trust, transactions cannot happen.**

---

I witnessed the transformation of Chinese e-commerce from a "trust desert" to a "trust oasis."

In 2003, when Alipay first launched, most people didn't dare to use it. "Pay online? It's a scam, right?"

In 2008, Alipay users exceeded 100 million. "Pay with Alipay, it's safe."

In 2013, mobile payments became widespread. People didn't carry wallets, only phones.

In 2018, my parents also started using Taobao. They don't understand what network effects are, but they know: things are cheap, delivery is fast, and you can return items if there are problems.

This is the value of technology—not concepts, but experience.

---

**Five years later, 2008**: Alipay connected to almost all mainstream banks. Taobao became China's largest e-commerce platform; eBay withdrew from China.

**2013**: Cainiao Network was established. **2014**: Alibaba listed on the NYSE with a first-day market cap of about $230 billion. Jack Ma became China's richest person.

**Twenty years later, 2023**: Live e-commerce rose. Douyin and Kuaishou restructured e-commerce with short videos.