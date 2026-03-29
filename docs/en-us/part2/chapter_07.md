# Chapter 7: Smoke on the Streets and VC Fuel

December 2008. Paris.

Travis Kalanick and Garrett Camp stood in the snow, waiting for a taxi.

They had just attended a tech conference and wanted to return to their hotel. But taxis in Paris were scarce; they waited nearly an hour before an empty cab stopped.

Camp complained: "If only there was an app that could summon a car with one click."

Kalanick was a serial entrepreneur. He had founded Scour, a file-sharing platform that went bankrupt after being sued. Then he founded Red Swoosh, a content delivery network acquired by Akamai. He was looking for his next venture.

Camp was the founder of StumbleUpon, which he had just sold to eBay. He too was looking for a new opportunity.

They discussed this idea on the streets of Paris: an app connecting passengers and drivers. Passengers tap a button on their phones, nearby drivers accept the request, and drive over to pick them up.

Back in San Francisco, they began developing the app. They found a third partner, Oscar Salazar, to handle technical development.

In June 2010, UberCab launched in San Francisco. Initially, it only partnered with limousine companies, offering premium transportation services. The price was higher than taxis, but the experience was better: black sedans, professional drivers, no cash needed.

In 2011, Uber began partnering with ordinary drivers, launching the UberX service. The price was cheaper than taxis, and anyone could become a driver.

Uber's expansion was astonishing. In 2011, Uber entered New York, Chicago, and Seattle. In 2012, Uber entered London, Paris, and Toronto. By 2015, Uber covered over 300 cities worldwide.

---

**Meanwhile, on the other side of the Earth.**

2012. Beijing.

Cheng Wei sat in an office in Zhongguancun, staring at data on his computer screen.

He was the founder of Didi Dache (Didi Taxi). A few months earlier, he had left Alibaba to start this company. His idea was simple: use mobile phones to hail taxis.

China's taxi industry had a pain point: it was hard to get a cab. During peak hours, bad weather, or in remote areas, it was almost impossible to find a taxi. Passengers stood by the roadside waving, while taxis drove past without stopping.

Didi's solution was to match taxi drivers and passengers through mobile phones. Passengers posted requests on the app, nearby taxi drivers accepted, and drove over to pick them up.

But Didi faced a problem: how to get taxi drivers to use the app?

At that time, smartphones weren't widespread among Chinese taxi drivers. Most drivers used feature phones that could only make calls and send texts.

Cheng Wei came up with a solution: he sent people to Beijing's taxi companies to give drivers smartphones and teach them how to use Didi. He also subsidized drivers: a few yuan for every ride accepted.

This strategy worked. Didi quickly became popular among Beijing's taxi drivers.

But Didi soon discovered that the taxi market was limited. The number of taxis was regulated by the government and couldn't increase arbitrarily. During peak hours, it was still impossible to get a ride.

Didi began to imitate Uber, launching a private car service. Anyone with a car and a driver's license could become a Didi driver.

This sparked conflict with regulatory authorities.

---

Ride-hailing platforms are typical representatives of the O2O model. They connect online user demand with offline physical services.

Users open the app; the app gets the user's location and displays it on a map. Users enter their destination; the app calculates the route and estimated price. Users tap "Request Ride"; the app sends requests to nearby drivers.

After a driver accepts, the app shows the driver's location, updating in real-time. Users can see how far away the driver is and the estimated arrival time.

All of this relies on LBS (Location-Based Services) technology.

GPS positioning: Phones obtain precise location through GPS, with accuracy within a few meters to tens of meters. But in urban canyons, GPS signals reflect, making positioning inaccurate.

Network positioning: Phones use Wi-Fi and cell tower signals to assist positioning. Wi-Fi positioning has higher accuracy; cell tower positioning has lower accuracy but can compensate for GPS shortcomings.

Inertial navigation: Phones use accelerometers and gyroscopes to detect movement direction and speed. When GPS signals are lost, inertial navigation can estimate position.

---

Ride-hailing platforms need to calculate optimal routes: from origin to destination, which road is fastest, shortest, cheapest?

Route planning is a classic algorithm problem. The most commonly used algorithms are Dijkstra's algorithm and A* algorithm.

Dijkstra's algorithm: Starting from the origin, gradually expand to adjacent nodes, calculating the shortest distance to each node. Time complexity is O(n²), too slow for large-scale road networks.

A* algorithm: Based on Dijkstra's algorithm, adds a heuristic function to prioritize expanding nodes more likely to reach the destination. Time complexity is greatly reduced.

But real-world road networks are more complex. Roads have directions, congestion, and traffic lights. Ride-hailing platforms need real-time traffic information to dynamically adjust routes.

Didi partnered with Amap (AutoNavi) to obtain real-time traffic data. Uber used the Google Maps API. Later, Didi acquired a mapping company and began developing its own maps and navigation.

---

The core algorithm of ride-hailing platforms is dispatching: how to assign orders to the most suitable drivers?

The simplest dispatching strategy is "nearest dispatch": assign the order to the closest driver. But this strategy has problems:

Fairness: If a certain area has many orders but few drivers, those drivers will receive a large number of orders while drivers in other areas receive none.

Efficiency: Nearest isn't necessarily optimal. If the closest driver is completing another order, it may take a long time before they can accept a new one.

User experience: Users may care more about waiting time than driver distance. A driver farther away but currently empty may arrive faster than a closer driver who is currently carrying a passenger.

Didi developed an "intelligent dispatch" system, comprehensively considering multiple factors:

Distance: Distance between driver and passenger.

Direction: Whether the driver is heading toward the passenger.

Driver status: Whether the driver is empty or carrying a passenger.

Historical data: The driver's past acceptance rate, completion rate, and rating.

User preferences: Some users prefer specific types of vehicles or drivers.

This is a multi-objective optimization problem. The platform needs to balance efficiency, fairness, and user experience.

---

Dynamic pricing is a controversial feature of ride-hailing platforms.

During peak demand, prices automatically increase to attract more drivers online and balance supply and demand. During low demand, prices decrease to attract more passengers.

Uber calls this "Surge Pricing"; Didi calls it "Dynamic Pricing."

The algorithm is simple: when the ratio of requests to available drivers exceeds a threshold, prices begin to rise. The greater the imbalance, the higher the price multiplier.

Dynamic pricing improves market efficiency but also triggers user backlash. Users feel "exploited" during peak times when prices are several times higher.

Kalanick's response was: "This is economics. High prices attract more supply, and prices will naturally fall."

But users don't accept this explanation. They want stable, predictable prices.

Didi faced similar controversy. During a heavy rainstorm in Beijing in 2016, Didi's prices surged several times, sparking online outrage.

Cheng Wei's response was: "We'll cap price increases and provide subsidies during extreme weather."

---

The subsidy war was the most brutal phase of China's ride-hailing market.

In 2014, Didi and Kuaidi (its main competitor) engaged in a subsidy war. Didi subsidized passengers 10 yuan per ride; Kuaidi subsidized 12 yuan. Didi subsidized drivers 50 yuan per day; Kuaidi subsidized 60 yuan.

Both sides burned through billions of yuan. Investors kept injecting capital, supporting this war of attrition.

In February 2015, Didi and Kuaidi merged to form Didi Kuaidi, later renamed Didi Chuxing (Didi出行). The subsidy war temporarily ended.

But Uber entered China. In 2015, Uber China launched, once again igniting the subsidy war.

Didi and Uber China burned through billions of dollars, vying for market share. In the end, Didi acquired Uber China; Uber took a stake in Didi and exited the Chinese market.

This war proved a rule: in markets with network effects, the winner takes all. The platform with the largest market share attracts the most users and drivers, forming a monopoly.

---

Regulatory gaming is an eternal theme for ride-hailing platforms.

Uber's entry into various cities faced resistance from taxi companies and regulatory authorities. Taxi companies protested that Uber was illegal operation; regulators issued bans.

Uber's response was: first enter the market, then negotiate with regulators. This "ask for forgiveness, not permission" strategy allowed Uber to rapidly expand globally.

But this strategy also brought risks. In 2017, Uber was banned in London. In 2019, Uber's license in London was temporarily revoked.

Didi faced greater regulatory pressure in China. Private car services were in a legal gray area; regulators repeatedly issued rectification notices.

In 2016, China legalized ride-hailing services but imposed strict restrictions: drivers must have local household registration, vehicles must meet certain standards, and platforms must obtain operating licenses.

These regulations increased Didi's operating costs but also provided legal protection.

---

In 2015, I first used Didi.

I was standing by the roadside in Beijing, unable to hail a taxi. I opened the Didi app, entered my destination, and within 10 seconds, a driver accepted.

Five minutes later, a white Volkswagen stopped in front of me. The driver was a young man who said he was a part-time driver and worked at an IT company during the day.

"Why do you drive part-time?" I asked.

"To earn some extra money," he said. "Didi's subsidies are good; I can earn a few hundred yuan on weekends."

That ride cost 25 yuan, but Didi subsidized 10 yuan. I actually paid 15 yuan.

I knew this subsidy wouldn't last forever. But at that moment, I enjoyed the convenience brought by capital.

---

**Five years later, 2015**: Uber covered 300+ cities globally; Didi acquired Uber China, dominating the Chinese market.

**Ten years later, 2020**: Didi faced data security investigations; Uber shifted focus to Uber Eats. Autonomous driving began testing.

**Twenty years later, 2030**: When autonomous driving is widespread, will human drivers still exist? When vehicles are shared rather than privately owned, will the concept of "hailing a ride" disappear?

The destiny of code depends on the people holding the keyboard.

And the next chapter of the story has just begun.