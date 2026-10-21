# Chapter 6: Empty Rooms Kidnapped by Algorithms and Hotels

October 2007. San Francisco.

Industrial designers Joe Gebbia and Brian Chesky couldn't afford their rent anymore. The rent was $1,150, and their bank account only had a few thousand dollars left. Engineer Nathan Blecharczyk later joined as the third co-founder.

Chesky wore a plaid shirt, his hair slightly messy. He was an industrial designer from New York, a graduate of the Rhode Island School of Design. Gebbia was his roommate, also from RISD, an industrial designer.

One weekend, San Francisco was hosting an international design conference, and hotels were fully booked. Chesky noticed many attendees couldn't find accommodation.

"Why don't we try?" Chesky said to Gebbia. "Put a few air mattresses on the apartment floor, provide accommodation and breakfast, charge $80 a night."

"We can't afford rent anyway; worst case, we still can't afford it."

Three guests came. They slept on the floor and ate pancakes Chesky made for breakfast. Chesky and Gebbia earned $240.

The floor business was born.

Chesky realized this wasn't just a contingency plan. It was a business model: there are countless empty rooms in the world, and countless travelers needing cheap accommodation. If they could connect them...

In August 2008, AirBed & Breakfast launched. In 2009, it received $20,000 in seed investment from Y Combinator. By 2011, bookings exceeded 1 million nights, with a valuation of $1 billion.

Chesky's design background deeply influenced Airbnb's product philosophy. Every interface pursued simplicity and elegance; every interaction aimed to be natural and smooth.

"We want users to feel like they're staying at a friend's house, not a hotel."

Trust became the currency.

---

**Meanwhile, on the other side of the Earth.**

1999. Shanghai.

Four men were eating hot pot in a restaurant, discussing a crazy idea.

James Liang, 31, graduated from Fudan University's youth class and later earned a Stanford economics PhD (around 2011). He wore glasses, spoke slowly, but his eyes sparkled with ambition.

Neil Shen, 32, Yale MBA, investment banker at Deutsche Bank. He wore exquisite suits, had agile thinking, and was extremely sensitive to numbers.

Ji Qi, 33, engineering master's from Shanghai Jiao Tong University, serial entrepreneur. He was energetic and had strong execution.

Min Fan, 33, master's from Shanghai Jiao Tong University, general manager of Shanghai Travel Service. He knew the travel industry deeply.

They were known as the "Four Gentlemen of Ctrip."

James Liang proposed an idea: use the internet to transform the tourism industry. At that time, Chinese people booked hotels and flights either at travel agency stores or by phone. Inefficient, opaque information.

"We can make a website," James Liang said, "letting users book hotels and flights directly online."

"Can this work in China?" Neil Shen asked. "Chinese people are used to face-to-face transactions; online payment isn't widespread."

"Precisely because it's not widespread, there's opportunity," James Liang said. "When everyone thinks it works, there won't be our opportunity."

In May 1999, Ctrip was founded.

Ctrip's model was completely different from Airbnb. Airbnb was C2C, connecting hosts and guests. Ctrip was B2C, connecting hotels and consumers.

But both solved the same problem: how to establish trust between strangers.

---

The essence of OTA is a platform connecting accommodations and travelers.

Hosts provide rooms, travelers need accommodation, the platform matches supply and demand and takes commission. This connection makes both sides promote each other: more hosts mean richer choices for travelers; more travelers mean hosts are more willing to join.

This is the manifestation of network effects—product value grows exponentially with the number of users.

But trust is fragile. Travelers worry: What if I pay and the host doesn't give me the key? Hosts worry: What if I give the key to a stranger and they steal my things?

Airbnb's solution is a two-way review system. Hosts review guests, guests review hosts. Good reviews accumulate reputation; bad reviews warn of risk.

But reviews have biases—most people give good reviews to avoid retaliation, and fake reviews are hard to eliminate. Airbnb uses "delayed publication" to deal with this: both parties' reviews are published simultaneously to prevent retaliatory bad reviews.

Ctrip's solution is brand endorsement. Ctrip signs agreements with hotels, ensuring real listings, transparent prices, and standard services. If problems occur, Ctrip is responsible for coordination and resolution.

Two models, two trust mechanisms. Airbnb relies on community self-governance; Ctrip relies on platform guarantees.

---

Real-time inventory synchronization is the lifeline of OTA.

Airbnb's listings are dynamic—individual hosts can change prices, adjust available dates, or even delist at any time. After a user books, that listing immediately becomes unavailable.

Imagine: a host in Tokyo has an apartment. He sets $100 per night on Airbnb, available next week. A user in New York is browsing, considering booking. At the same time, a user in London has already clicked the "Book" button.

The system must make a decision in milliseconds: assign the room to the London user while telling the New York user "already booked."

This requires distributed locks. Locking this record at the database level prevents concurrent conflicts. Airbnb uses Redis to implement distributed locks, ensuring the same room isn't double-booked.

Ctrip faces a B2C scenario. Hotels use PMS systems to manage inventory; Ctrip's "Room Status Connect" interfaces with PMS, synchronizing prices and inventory in real-time. Price conflicts across multiple channels are a problem Ctrip must solve.

---

Search ranking determines conversion rates.

Ranking algorithms consider: relevance (location, price, room type match), quality (ratings, response speed), conversion rate (historical booking data), commission contribution.

Airbnb's "Superhost" badge and Ctrip's user profile recommendations are both weighted factors in ranking.

The platform's goal is to maximize GMV (Gross Merchandise Value) while ensuring user experience. This is a multi-objective optimization problem.

---

Dynamic pricing is the core algorithm of OTA.

Hotel room prices aren't fixed; they fluctuate based on supply and demand. During peak seasons, prices rise; during off-seasons, prices fall. On weekends, business hotels are cheap; on weekdays, resort hotels are cheap.

Airbnb's pricing is determined by hosts, but the platform provides pricing suggestions. The algorithm analyzes historical booking data, competitor prices, local events, and seasonality to recommend optimal prices.

Ctrip's pricing is determined by hotels, but the platform has bargaining power. Large OTAs can negotiate lower prices with hotels and then mark up to consumers.

Dynamic pricing is a double-edged sword. It improves resource utilization but may also trigger consumer backlash. When consumers find that prices change based on their browsing history, they feel "discriminated against."

---

The hardware foundation of OTA is the smartphone.

GPS positioning allows users to find nearby listings. Camera allows hosts to upload photos. Mobile payment allows instant booking confirmation.

Without smartphones, the OTA model wouldn't exist.

---

In 2015, I first used Airbnb.

I was traveling in Tokyo and booked a small apartment in Shibuya. The host was a Japanese designer who left the key in a mailbox and sent me the password via the app.

When I opened the door, the room was small but exquisite. IKEA furniture, Muji bedding, a small balcony with a view of the Tokyo skyline.

I felt like I was living in Tokyo, not visiting Tokyo.

That feeling was completely different from staying in a hotel. Hotels are standardized; Airbnb is personalized. Hotels are commercial; Airbnb is life.

But I also encountered problems. Once in Bangkok, the listing photos looked great, but the actual place was old and dirty. I gave a bad review, and the host retaliated with a bad review of me.

Trust is fragile. Once broken, it's hard to repair.

---

**Five years later, 2012**: Airbnb acquired 10 million nights booked; Ctrip went public on NASDAQ with a market cap exceeding $10 billion.

**Ten years later, 2017**: Airbnb entered China but faced fierce competition from local platforms like Tujia and Xiaozhu. Ctrip acquired Skyscanner and became a global travel giant.

**Twenty years later, 2027**: When VR travel becomes widespread, when the metaverse replaces physical travel, will OTA still exist?

The destiny of code depends on the people holding the keyboard.

And the next chapter of the story has just begun.