# Chapter 4: The Lego in the Garage and the Lights of the Resource Hotel

Autumn 1996. The computer science building at Stanford University was filled with the smell of coffee and old books.

Larry Page and Sergey Brin were arguing about a problem. One was quiet and introverted, the other outgoing and talkative. They met at Stanford and became research partners. That afternoon, Page drew a diagram on the blackboard—the link relationships between web pages. One arrow pointing to another, like a complex web.

"If page A links to page B, it means A thinks B has value," Page said, the chalk making a harsh sound on the blackboard. "The more links a page receives, the more important it is."

Brin stared at the blackboard for a long time: "But the problem is, links have different quality. Being linked by The New York Times is different from being linked by some obscure blog."

They came up with a recursive solution: votes from important pages carry more weight. But to calculate the importance of each page, they needed to solve a huge system of equations—billions of unknowns.

Page built a server with Lego blocks. Real Lego—colorful plastic blocks he bought from a toy store, used to secure hard drives and motherboards. That server sat in the corner of the dorm room, humming away, crawling all the web pages on Stanford's campus network.

They named this prototype "BackRub"—because it analyzed back links.

In September 1998, in Susan Wojcicki's garage, Google was founded. The name came from "googol"—10 to the power of 100, symbolizing the ambition to organize infinite information.

Susan Wojcicki later became CEO of YouTube. But in that autumn, she was just an ordinary landlord renting her garage to two Stanford PhD students. She would never have imagined that this garage would later become one of Silicon Valley's most legendary startup origins.

---

**Meanwhile, on the other side of the Earth.**

January 2000. Beijing. The cold wind was biting.

In a room at the Peking University Resource Hotel, 32-year-old Robin Li stared at the computer screen.

The room had only one bed, one desk, and one computer. Several handwritten papers were taped to the wall, showing Chinese word segmentation charts—how to cut continuous Chinese characters into meaningful words.

Robin Li had just returned from Silicon Valley. He had worked there for several years, first at Dow Jones, then at Infoseek. He saw the potential of search engines and also saw the inevitable failure of American search engines in the Chinese market.

Why?

Because they didn't understand Chinese.

English words have spaces between them; "Hello World" is naturally two words. But Chinese has no spaces. Is "北京大学" (Peking University) one word or two? How does a computer know?

And there was that chaos of character encoding—some websites used GB2312, some GBK, some Big5, some UTF-8. The same Chinese character was different binary numbers under different encodings. American search engines saw a mess of garbled text and crashed.

Robin Li invented the "RankDex" algorithm in 1996, even earlier than PageRank. But he didn't start a business; he chose to work in Silicon Valley.

Now, he was back.

The room was cold. Robin Li wrapped his coat tighter and typed the first line of code on the keyboard. He didn't know that this simple hotel room would become one of the most legendary starting points in Chinese internet history.

In May 2000, Baidu Search went live.

---

Let's return to Stanford in 1996.

At that time, search engines like AltaVista, Lycos, and Excite all worked the same way: keyword matching. Whatever the user input, the system returned web pages containing those words.

The problem was, there might be millions of web pages containing a certain keyword. For example, searching for "Java" could mean the Java programming language, could mean the island of Java, or could mean coffee. Search engines at the time didn't know how to distinguish, so they just piled all pages containing "Java" on the user.

More troublesome was that web authors quickly discovered the loophole: as long as they repeated "Java" a thousand times on their page, they could rank first. This cheating technique was called "keyword stuffing."

Page was thinking about another question: why can humans easily judge which web page is more important?

The answer is simple: we trust authority. If The New York Times says a website is worth noting, we'll pay attention; if a university professor's personal blog recommends an article, we might take a look.

But computers don't "trust." They need a computable method to measure importance.

The formula Page wrote on the blackboard, later called PageRank, is actually quite simple:

A web page's PageRank value = the sum of PageRank values of all pages linking to it, divided by the number of outbound links from those pages.

In other words, if page A links to page B, then A passes part of its "importance" to B. The more pages A links out to, the less "importance" each page receives.

This is a recursive definition—to calculate A's importance, you first need to know the importance of all pages linking to A; to know the importance of those pages, you need to know the importance of pages linking to them...

Mathematically, this is equivalent to solving a huge system of linear equations. For billions of web pages, this computation is staggering.

But Page and Brin discovered a clever method: iterative calculation. First give each web page an initial value (say, 1), then repeatedly apply that formula until the values converge.

This process is like a group of people in a room passing balls to each other. At first, everyone holds a ball, then passes balls to others according to the rules. After enough rounds, the number of balls each person holds stabilizes—that's their PageRank value.

Google's servers hummed late into the night, calculating the PageRank values of the entire internet. That humble server built with Lego blocks was doing something unprecedented: ranking the entire internet.

---

Meanwhile, in the Resource Hotel in Beijing, Robin Li faced another problem.

Chinese search is much harder than English search.

First is word segmentation. Should "北京大学" be segmented as "北京/大学" (Beijing/University) or "北京大学" (Peking University)? "上海市长江大桥"—is it "上海市/长江/大桥" (Shanghai City/Yangtze River/Bridge) or "上海/市长/江大桥" (Shanghai/Mayor/Jiang Daqiao)? Different segmentation methods lead to completely different search results.

Robin Li's solution was the bidirectional maximum matching algorithm: start from the left, find the longest matching word; then start from the right, find the longest matching word; then compare the two schemes and choose the better one.

This required a dictionary. Baidu's early engineers manually compiled a large number of words, building a huge Chinese dictionary.

Then came encoding conversion. Baidu needed to identify the encoding of web pages, then uniformly convert them to the internal encoding. This is like translation—first translate various dialects into Mandarin, then process.

Robin Li also faced a more fundamental problem: there was too little Chinese internet content.

In 2000, China had only a few thousand websites, while the US had millions. This meant that even if Baidu indexed all Chinese web pages, there would still be far fewer search results than Google.

Robin Li's solution was: start with portal site search. Sina, Sohu, and NetEase were the largest Chinese websites at the time; Baidu provided them with on-site search services. When users searched on Sina, the backend called Baidu's technology.

This allowed Baidu to quickly acquire users and accumulate data.

---

In 1999, Google was still a company without revenue.

Page and Brin insisted on not doing advertising. They believed advertising would affect the fairness of search results. If Microsoft paid Google to rank its website first, then Google wouldn't be a search engine but an advertising platform.

But investors didn't think so. Google had burned through millions of dollars in venture capital and needed to find a profit model.

In October 2000, Google launched AdWords.

This was a keyword advertising system. Advertisers could buy keywords, and when users searched for these words, ads would appear next to the search results.

But AdWords had an innovation: ad ranking wasn't determined solely by bid, but also by click-through rate.

If an advertiser bid high but no one clicked their ad, their ranking would drop. Conversely, if an advertiser bid lower but their ad was popular (high click-through rate), their ranking might be higher.

This mechanism ensured ad relevance. Advertisers were motivated to place ads relevant to user queries rather than spam ads.

Google's charging model was also clever: pay-per-click (PPC). Advertisers didn't pay for impressions, only for actual clicks. This gave advertisers clear ROI measurement.

The money printing machine started.

In 2001, Google's revenue was $86 million. In 2002, it grew to $440 million. In 2003, it reached $1.47 billion. When it went public in 2004, revenue had exceeded $3 billion.

Google's business model had a characteristic: the cost of serving each additional user was almost zero.

Each additional ad impression cost Google only a bit of server electricity and bandwidth. But advertisers were willing to pay for each click. This meant that the larger Google's scale, the higher its profit margin.

This was unimaginable for traditional manufacturing. A car factory consumes steel, rubber, and labor for every additional car produced; but Google serves each additional user at almost no additional cost.

---

Meanwhile, Baidu was exploring its own business model.

Robin Li also didn't want to do advertising at first. He tried enterprise search services—customizing search engines for large companies and charging for deployment. But this market was too small, with limited revenue.

In 2001, Baidu launched paid search ranking. Advertisers could bid for keywords; the higher the bid, the higher the ranking.

But Baidu's approach was more aggressive than Google's: ads not only appeared next to search results but were directly inserted into the search results list, mixed with organic results.

This caused controversy at the time. Users found it hard to distinguish which were organic search results and which were ads.

In 2008, CCTV exposed Baidu's paid search ranking problem with false medical ads. Some unqualified medical institutions appeared at the top of search results through paid ranking, misleading patients. Baidu's stock price plummeted, and Robin Li was forced to rectify.

Later, Baidu labeled ads with "推广" (promoted), but the boundary between ads and organic results remained blurry.

Behind this crisis was a deeper problem: search engines had too much power.

Most people don't flip through search results; they only look at the first page, or even just the top three. Search engines determine what information users see and don't see.

This power is enormous. It can shape public perception and influence the direction of public opinion.

Google's motto was "Don't be evil." This motto reflected Google's awareness of its own power: search engines should be fair and transparent, not manipulating search results.

But "Don't be evil" is a vague standard. What is evil? Who decides?

In 2006, Google entered China, launching the Chinese version of Google Search. But four years later, in 2010, Google announced its withdrawal from mainland China, moving search services to Hong Kong.

The official reason was: Google suffered cyber attacks from China and was unwilling to continue self-censoring search results.

This was a landmark event. Chinese netizens had to rely more on Baidu.

Baidu's search results quality was uneven. For many keywords, the top results were all ads. Sometimes, the entire first page was ads. This experience made many people miss Google.

But Baidu also had its advantage: it understood Chinese better.

Baidu's Box Computing allowed users to complete some operations directly in the search box, such as checking weather, checking stocks, or translating. This reduced user operation steps and improved experience.

Baidu also launched products like Baidu Zhidao (Baidu Knows) and Baidu Baike (Baidu Encyclopedia), building a content ecosystem. Users could not only search on Baidu but also ask questions, answer, and learn.

But the search market landscape was changing.

After 2010, smartphones began to spread. User search behavior underwent a fundamental shift.

In the PC era, search was the entry point to the internet. Users opened browsers, entered search terms, and found websites.

In the mobile era, apps became the entry point. Users opened Taobao to search for products, Dianping to search for restaurants, Ctrip to search for hotels. The status of general search engines declined.

Baidu faced challenges in the mobile era. Users no longer searched for everything through Baidu but opened specific apps directly. Baidu tried to transform, acquiring 91 Wireless (an app store) and developing the Mobile Baidu app, but with limited results.

By 2020, Baidu's market share in China's search market still exceeded 70%, but search's proportion of users' internet usage time had dropped significantly.

---

Search is a compute-intensive application. It requires large amounts of CPU, memory, and storage.

In the 1990s, the server market was dominated by RISC architectures: Sun's SPARC, IBM's POWER, HP's PA-RISC. These processors were powerful but expensive, with a single machine possibly costing hundreds of thousands of dollars.

From day one, Google made a different choice: using cheap x86 servers.

They didn't buy single high-performance mainframes but bought hundreds or thousands of cheap ordinary PC servers. Each server had an Intel CPU, a few sticks of memory, a few hard drives, then stacked on racks.

This was a "scale-out" architecture. Rather than buying one supercomputer, buy a thousand ordinary computers and connect them into a cluster with software.

This architecture had a premise: software must assume hardware could fail at any time. Hard drives break, memory errors occur, CPUs crash. Google's engineers designed a set of fault-tolerance mechanisms: data is backed up on multiple servers; if one server dies, others take over.

What if a server breaks?

Throw it away, replace it. Cost is only a few thousand dollars.

In comparison, if a Sun mainframe broke, professional engineers needed to be called for repair, with downtime possibly lasting several hours.

Google's data center is a magical place. No brand-name servers, just rows of racks stacked with white-box servers assembled in a Lego-block style. The air conditioning is cranked up because the heat from thousands of servers is astonishing.

This architecture costs one-tenth of traditional data centers but doesn't lag in performance.

Baidu's data centers also adopted similar architectures. But due to the special circumstances of China's internet, Baidu faced another challenge: international bandwidth was too expensive.

In the 2000s, China's international internet export bandwidth was very limited. Users accessing foreign websites was slow because data had to pass through crowded international fiber optic cables.

Baidu deployed servers throughout China, letting users access the nearest servers. This reduced latency and improved search speed.

But this also meant Baidu needed to build large numbers of data centers itself. This was a huge capital expenditure.

---

Meanwhile, another processor architecture was quietly rising.

ARM, a British company, designs low-power processor architectures. ARM doesn't manufacture chips itself but licenses designs to chip manufacturers. Qualcomm, Apple, and Samsung all use ARM architecture to design their own chips.

ARM's characteristic is low power consumption. Compared to Intel x86's 100+ watt power consumption, ARM chips need only a few watts. This makes ARM the first choice for mobile devices—smartphones need to save power.

But ARM had almost no presence in the server market. Servers need high performance, not power saving.

The situation began to change in the 2010s.

Data center electricity costs became huge expenses. A 100-watt server costs hundreds of dollars in electricity per year. If a data center has hundreds of thousands of servers, electricity costs are hundreds of millions of dollars.

The low-power characteristics of ARM chips began to attract data center operators' attention.

In 2018, Amazon launched the ARM-based Graviton processor for AWS cloud services. In 2020, Apple announced that Mac computers would use the self-developed ARM chip M1.

ARM is penetrating from mobile to server and desktop.

---

Storage technology is also revolutionizing.

Traditional hard disk drives (HDD) use rotating disks and moving heads; read-write speed is limited by physical mechanics. Solid-state drives (SSD) use flash memory chips, with no moving parts; read-write speed is dozens of times faster than traditional hard drives.

Google began large-scale use of SSDs in the 2010s. Index data is stored on SSDs, reducing query response time from hundreds of milliseconds to tens of milliseconds.

But SSDs have a problem: they're expensive. For the same capacity, SSDs cost several times more than traditional hard drives.

Google's solution was tiered storage: hot data (frequently accessed data) is stored on SSDs, cold data (rarely accessed data) is stored on traditional hard drives. This guarantees performance while controlling costs.

Baidu established similar storage architectures in China. Because Chinese users are more accustomed to searching for long-tail queries, Baidu's proportion of hot data is higher, and SSD usage is also greater.

---

I first used Google on an afternoon in 2009.

At that time, I had just started university. The computers in the school lab were still old LCD monitors with thick bezels, screens glowing with a faint blue light. The air conditioning in the lab was cranked up because the heat from dozens of computers made the room stuffy.

Before that, I used Baidu. Searching for technical problems often required flipping through several pages to find useful information.

That day, a senior told me: "Try Google, it's much better than Baidu."

I opened the browser and typed google.com in the address bar. The international export of the education network was slow; the page took more than ten seconds to load.

I searched for a programming problem—how to implement a linked list in C.

The moment the search results came out, I was stunned.

The first result was the answer from an English technical blog, as precise as if someone had known in advance what I was going to ask. I clicked in; the page loaded quickly, the answer clear and concise.

That feeling was like suddenly walking from darkness into a bright room.

From that day on, I knew about Google.

Later, I understood why Google's search results were so good. Not just because its algorithm was smarter, but because its crawlers covered the entire English-language internet, while Chinese search engines only covered a small part of China.

The asymmetry of information was planted from that moment.

In 2012, I started interning. The technical team at the company all used Google to search for technical problems and Baidu to search for Chinese news. We had an unspoken understanding: technical problems go to Google, life problems go to Baidu.

In 2014, Google became almost inaccessible in mainland China. The day the news came, there was a collective sigh in the office.

"What do we do now?" someone asked.

"Use a VPN," another person said.

That night, I spent an hour configuring a VPN. From then on, my browser always had that little lock icon.

I wasn't trying to access any sensitive content. I just wanted to search for technical problems, get the latest technical documentation, access GitHub and Stack Overflow.

These sites weren't blocked. But Google was blocked, and Google was the bridge to these sites.

---

Search engines are not just tools. They are gatekeepers of information, entry points to knowledge.

When you master a search engine, you master the power to define truth. You can decide what information is important and what can be ignored. You can decide what users see and don't see.

Google's "Don't be evil" motto is a self-constraint on this power. But the temptation of power is enormous. Even Google couldn't help probing at the edges.

In 2018, Google was exposed for considering re-entering the Chinese market and developing a search product compliant with Chinese censorship requirements called "Project Dragonfly." This project sparked intense internal controversy and was eventually shelved.

That same year, Google employees protested the company's participation in the US military's drone project, Project Maven. Google eventually withdrew from this project.

These events show that even Google struggles between commercial interests and social responsibility.

And Baidu, with its leading position in the Chinese market, faced another temptation: how to use this position to gain more commercial interests?

Paid search ranking, medical ads, content farms... these issues repeatedly pushed Baidu to the forefront of public opinion.

The war of search engines was never just a war of technology. It was a war of business models, a war of values, a war of information power.

Code is neutral. But the people who write the code, the companies that operate the code, are not neutral.

---

**August 19, 2004**: Google listed on NASDAQ.

Opening price $85, closing price $100.34. Company market cap $27 billion.

Page and Brin wrote a letter at the IPO, beginning with: "Google is not a conventional company. We do not intend to become one."

They insisted on a dual-class share structure: Class A shares with 1 vote per share, Class B shares with 10 votes per share. Page, Brin, and CEO Schmidt held most of the Class B shares, ensuring their control over the company.

This decision allowed Google to adhere to long-termism, unaffected by short-term stock price fluctuations.

But this decision also gave founders enormous power. They could decide Google's direction without shareholder constraints.

The concentration of power is a double-edged sword. It can bring vision, or it can bring disaster.

---

**Five years later, 2009**: Microsoft launched the Bing search engine, investing billions of dollars to challenge Google. But Google's market share still exceeded 65%. The winner-takes-all pattern in the search market had emerged—the larger the market share, the easier it is to acquire more resources, further widening the gap with competitors.

The result of network effects: product value grows exponentially with the number of users. The search engine market shows a "winner-takes-all" pattern—more users → more data → more accurate algorithms → more users.

**Ten years later, 2014**: Google reorganized into Alphabet; Page and Brin retreated behind the scenes, handing daily management to Sundar Pichai. But control remained in their hands.

**Twenty years later, 2024**: OpenAI launched ChatGPT, and Google launched Gemini. Search is shifting from "keyword matching" to "conversational AI." But the essence of search hasn't changed: helping users find the information they want.

**Thirty years later, 2054**: When AI can directly answer all questions, do search engines still exist? When large models can generate any content, how do we distinguish truth from falsehood?

The destiny of code depends on the people holding the keyboard.

And the next chapter of the story has just begun.