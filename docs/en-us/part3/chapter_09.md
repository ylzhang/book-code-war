# Chapter 9: Retinal Feeding That Cuts Off Search

March 2012. Zhichun Road, Beijing.

Zhang Yiming sat in a rented apartment, staring at code on his computer screen.

He wore a gray plaid shirt, sleeves casually rolled up to his forearms. This was his signature attire—simple, plain, without any excess design. On his desk were only a MacBook Pro, a cup of cold coffee, and a stack of draft paper filled with formulas. A handwritten sticky note on the wall read: "Delayed Gratification."

Zhang Yiming was the founder of Toutiao. A few months earlier, he had left 99fang (a real estate vertical search site) to start this company. His idea was simple: use algorithms to recommend news.

At that time, news clients were all manually edited. Editors selected news; users passively read. Zhang Yiming believed this method was inefficient. Everyone has different interests; why should they read the same news?

His idea was: use algorithms to analyze user behavior and recommend content users are interested in. When a user clicks an article, the algorithm learns the user's preferences and recommends similar articles.

Zhang Yiming believed in algorithms. He often said: "Algorithms have no values, but algorithms have results." He believed that rather than letting editors decide what users see, algorithms should decide based on user behavior. This was a kind of "delayed gratification"—users might not know what they want, but the algorithm does.

After Toutiao launched, user numbers grew rapidly. By the end of 2012, daily active users exceeded 1 million. By 2014, daily active users exceeded 10 million.

But Toutiao faced a question: recommendation algorithms would lead to "information cocoons." Users only see content they like and don't see different viewpoints. This exacerbates social division.

Zhang Yiming's response was: algorithms are just tools; they satisfy user needs. Users want to see what, algorithms recommend what.

---

**Meanwhile, on the other side of the Earth.**

September 2016. Los Angeles.

An app called Musical.ly was exploding among American teenagers. Users could record 15-second short videos, add music, and share with friends.

Musical.ly's founders were two Chinese: Alex Zhu and Luyu Yang. They developed this app in Shanghai and unexpectedly became popular in the American market.

ByteDance noticed Musical.ly. In November 2017, ByteDance acquired Musical.ly for nearly $1 billion, merged it with their short video app Douyin, and launched the international version TikTok.

TikTok's spread was astonishing. In 2018, TikTok became the most downloaded app in the US. By 2019, TikTok's global monthly active users exceeded 1 billion.

TikTok's success marked the first breakthrough of a Chinese internet company in the global market.

---

Recommendation algorithms are ByteDance's core competitiveness. They determine what content users see and ByteDance's commercial value.

### Collaborative Filtering: Learning Preferences from User Behavior

The foundation of recommendation algorithms is collaborative filtering.

The core idea of collaborative filtering is: if two users have had similar behaviors in the past, they will have similar preferences in the future.

For example, both User A and User B have watched the movies *Titanic* and *Avatar*, so other movies User A likes, User B might also like.

There are two ways of collaborative filtering:

**User-based**: Find other users similar to the target user and recommend content these users like.

**Item-based**: Find other content similar to what the target user likes and recommend it to the user.

The advantage of collaborative filtering is simplicity and intuitiveness. But the disadvantages are also obvious:

**Cold start**: New users have no behavioral data, so recommendations cannot be made. New content has no user interaction, so it cannot be discovered.

**Sparsity**: Users only interact with a very small portion of content; the data matrix is very sparse, and recommendation effectiveness is poor.

**Popularity bias**: Popular content is recommended more, while long-tail content is difficult to discover.

ByteDance adopted more advanced recommendation algorithms: deep learning.

### Deep Learning Recommendation: From Features to Prediction

The core of deep learning recommendation models is: represent users and content as vectors and calculate the similarity between vectors.

**User vector**: Contains user age, gender, location, historical behavior, and other features. These features are encoded into a high-dimensional vector.

**Content vector**: Contains content title, body, images, video, tags, and other features. These features are also encoded into a high-dimensional vector.

**Prediction**: Calculate the similarity between user vector and content vector (such as dot product) to predict the user's interest level in the content.

ByteDance developed multiple deep learning recommendation models:

**Wide & Deep**: Combines linear models and deep models. Linear models memorize historical feature combinations; deep models generalize new feature combinations.

**DeepFM**: Combines Factorization Machines (FM) and deep neural networks. FM captures second-order interactions between features; deep networks capture high-order interactions.

**DIN (Deep Interest Network)**: Dynamically adjusts user interest vectors based on candidate content. Users have different interests for different types of candidate content.

Training these models requires massive amounts of data. ByteDance processes hundreds of petabytes of data daily; training models requires thousands of GPUs.

### Real-time Recommendation: Millisecond-level Response

When users open Toutiao or TikTok and refresh the content stream, the system needs to select dozens of items from millions of content pieces to recommend to the user within milliseconds.

This is a huge engineering challenge.

ByteDance developed a real-time recommendation system, including the following components:

**Recall layer**: Quickly screens thousands of candidate items from millions of content pieces. The recall layer uses multiple strategies: collaborative filtering recall, vector recall, popular recall, geographic location recall, etc.

**Ranking layer**: Performs fine-grained ranking on thousands of candidate items. The ranking layer uses deep learning models to predict user click-through rate, viewing time, interaction rate, and other metrics for each piece of content.

**Re-ranking layer**: Adjusts ranking results. The re-ranking layer considers diversity, freshness, timeliness, and other factors to avoid users seeing similar content consecutively.

The entire process needs to be completed within 100 milliseconds. ByteDance developed high-performance computing frameworks, using GPU acceleration for inference and caching to reduce database access.

### Content Understanding: From Text to Multimodal

Recommendation algorithms need to understand content. Only by understanding content can it be accurately recommended to interested users.

ByteDance developed multiple content understanding technologies:

**Text understanding**: Performs word segmentation, entity recognition, topic classification, and sentiment analysis on article titles and bodies.

**Image understanding**: Performs object detection, scene recognition, face recognition, and OCR (optical character recognition) on images.

**Video understanding**: Performs keyframe extraction, action recognition, speech recognition, and subtitle recognition on videos.

These technologies allow ByteDance to understand the multimodal features of content, improving recommendation accuracy.

---

ByteDance's rise challenged the dominance of Google and Facebook.

### Su Hua and Kuaishou's Inclusive Philosophy

While ByteDance was racing ahead, another company was doing recommendations with a completely different philosophy.

In 2011, GIF Kuaishou was still a tool for making GIF animations. Founder Su Hua looked at backend data and found that users were not only using Kuaishou to make animations but also sharing life clips.

Su Hua wore black-rimmed glasses and spoke slowly. He had worked at Google, participating in search engine development. He knew the power of technology and its limitations.

"Algorithms shouldn't only serve head users," Su Hua said. "Everyone deserves to be seen."

In 2013, Kuaishou transformed into a short video community. Unlike Douyin's "centralized recommendation," Kuaishou adopted a "decentralized" recommendation strategy: everyone has a chance to be recommended, not just influencers who already have fans.

Su Hua believed in "inclusiveness." He believed technology should benefit ordinary people, not just elites. Kuaishou's recommendation algorithm deliberately gives traffic to newcomers, giving ordinary people's videos a chance to be seen.

This philosophy brought a different community atmosphere. Kuaishou's users are more下沉 (lower-tier), more authentic, more like a "digital version of a county town." Douyin is more fashionable, more refined, more like a "digital version of a first-tier city."

By 2020, Kuaishou's daily active users exceeded 300 million, becoming China's second-largest short video platform.

Zhang Yiming and Su Hua represent two philosophies of recommendation algorithms: efficiency and inclusiveness. Douyin pursues letting users see the most interesting content; Kuaishou pursues giving everyone a chance to be seen. Neither philosophy is right or wrong; they are just different choices.

### Search vs. Recommendation

Search and recommendation are two different ways of obtaining information.

**Search**: Users actively input queries; the system returns relevant results. Users know what they are looking for.

**Recommendation**: The system actively pushes content; users passively receive. Users may not know what they want.

Search is "people finding information"; recommendation is "information finding people."

Google is the king of search. Its business model is: users search for keywords; Google returns search results and ads.

ByteDance is the king of recommendation. Its business model is: users open the app; the system recommends content and ads.

Recommendation is more efficient. Users don't need to think about what to search for; they just swipe the screen, and content continuously emerges.

Algorithms took over.

But recommendation also has problems. Users may fall into "information cocoons," only seeing content they like and not seeing different viewpoints. Users may be "kidnapped by algorithms," spending large amounts of time scrolling through short videos, unable to stop.

You are kidnapped.

### TikTok vs. Facebook

TikTok's success threatened Facebook's position.

Facebook's core product is News Feed: updates from friends and pages users follow, displayed in chronological or algorithmic order.

TikTok's core product is For You: the system recommends short videos based on user interests, without needing to follow any accounts.

TikTok's model is more suitable for content consumption. Users don't need to maintain social relationships; they just consume content. Content creators don't need to accumulate fans; they just need to make good content, and the algorithm will recommend it to interested users.

Facebook recognized the threat. In 2018, Facebook launched Lasso, a short video app imitating TikTok. But Lasso failed and closed in 2020.

In 2020, Facebook launched Reels in Instagram, a short video feature. Reels achieved some success but still couldn't compete with TikTok.

Facebook also tried to suppress TikTok through political means. In 2020, the Trump administration threatened to ban TikTok, requiring ByteDance to sell TikTok's US business. But this ban was blocked by courts and ultimately not enforced.

By 2023, TikTok's global monthly active users exceeded 1.5 billion, becoming the world's most popular short video platform.

The landscape changed.

### China's Reverse Export to the Global Market

TikTok's success marked the first time Chinese internet companies achieved a breakthrough in the global market.

Before this, Chinese internet companies mainly operated in the Chinese market. They imitated American companies' products and succeeded in the Chinese market. But they rarely competed with American companies in the global market.

ByteDance changed this pattern. TikTok is not an imitation of American products but an original product form. It competes head-to-head with American companies in overseas markets and won.

This is not only commercial success but also a cultural breakthrough. TikTok made global users accustomed to Chinese companies' products and accept Chinese companies' rules.

Of course, TikTok also faces challenges. The US government continues to pressure TikTok on data security grounds. The Indian government has already banned TikTok. European regulators are also investigating TikTok's data processing methods.

ByteDance is working hard to address these challenges, including data localization, transparency centers, and partnerships with US companies.

---

The prosperity of short videos cannot be separated from the support of mobile networks.

### 4G: The Foundation of the Video Era

In 2013, China issued 4G licenses. 4G network downlink speeds reached over 100Mbps, dozens of times faster than 3G.

4G made video consumption possible. In the 3G era, watching videos required buffering, with poor experience. In the 4G era, videos could play smoothly, and users began to get used to watching videos on their phones.

Douyin and Kuaishou rose in 2016, precisely when 4G was becoming widespread. Without 4G, there would be no prosperity of short videos.

4G also reduced traffic costs. In the 3G era, traffic fees were high, and users didn't dare to watch videos casually. In the 4G era, carriers launched unlimited data plans, and users could confidently consume video content.

### 5G: Higher Definition, More Real-time

In 2019, China issued 5G licenses. 5G network downlink speeds reached over 1Gbps, ten times faster than 4G.

5G makes higher-definition video possible. 4K and 8K videos can play smoothly on phones. VR (virtual reality) and AR (augmented reality) content can be transmitted in real-time.

5G also reduces latency. 4G network latency is tens of milliseconds; 5G network latency can be as low as a few milliseconds. This makes real-time interaction possible: live streaming, cloud gaming, remote control.

But 5G's impact on short videos is not as significant as 4G. Short videos are already smooth enough; users don't have strong demand for higher-definition video. 5G's killer app has not yet appeared.

### Computing Power Battle: GPU Clusters for Recommendation Systems

Recommendation algorithms are not just code. Behind them is terrifying hardware investment.

ByteDance has built multiple ultra-large-scale data centers in China. Just in Tianjin, the data center cluster deploys tens of thousands of NVIDIA GPUs. Recommendation system training clusters use A100/H100 GPUs, with each card priced at over $20,000. Training a complete recommendation model once requires thousands of GPUs computing in parallel for days.

But training is just the tip of the iceberg. Inference is the real cost black hole. Every time a user refreshes the information stream, the recommendation system needs to complete the three-level pipeline of recall, ranking, and re-ranking within 100 milliseconds. Global daily active users exceed 1.5 billion, each person refreshing hundreds of times per day—this means tens of millions of inference requests per second. ByteDance has deployed dedicated inference clusters for this, extensively using NVIDIA T4 inference cards. Each T4 consumes only 70 watts, but INT8 inference performance reaches 130 TOPS.

The computing power consumption of recommendation systems forms a sharp contrast with search systems. Google Search is "user-initiated, system-responds" one-time computing; ByteDance's recommendation is "system-initiated, continuous feeding" never-ending computing. Search costs are proportional to query volume; recommendation costs are proportional to user dwell time. The longer users scroll, the more GPUs burn. Computing power is the oil of the recommendation empire, and the pricing power of oil is in NVIDIA's hands.

### Base Station Density and Video Bitrate: Hard Constraints of the Physical World

The smooth experience of short videos depends not only on phones and servers but also on the invisible "air pipe" between them.

A 15-second 720p short video is about 2-3MB; 1080p is about 5-8MB. Users consume 1-3GB of traffic per hour watching videos. This puts stringent requirements on mobile networks: single-user downlink rates need at least 10Mbps or above to achieve "zero buffering" experience.

A 4G base station's single sector capacity is about 100-150Mbps, theoretically capable of serving 10-15 high-bitrate video users simultaneously. But in densely populated urban CBDs or subway cars, hundreds of people may be scrolling through videos within a base station's coverage area. Base station overload, bitrate automatically degrades, picture becomes blurry.

China's three major carriers frantically built base stations for this. As of 2023, China has over 6 million 4G base stations and over 3 million 5G base stations—the densest mobile network in the world. This is no accident. Short video app DAU data directly drives carriers' base station investment plans. Every additional daily active user for ByteDance corresponds to a few extra watts of RF power on a base station antenna.

On the phone side, video decoding chips are also evolving. Qualcomm Snapdragon 8 series and MediaTek Dimensity 9000's built-in hardware H.265/H.266 decoders can complete decoding of a 1080p video frame in less than 10 milliseconds, with power consumption only one-tenth of software decoding. These tiny hardware modules embedded in SoCs are the most easily overlooked physical foundation of the short video empire.

### CDN: Content Distribution

Short videos require massive bandwidth. Every time a user scrolls through a video, they need to download several MB of data. If hundreds of millions of users scroll through videos simultaneously, bandwidth costs are enormous.

ByteDance uses CDN (Content Delivery Network) to reduce bandwidth costs.

CDN deploys edge nodes globally, with each node caching popular content. When users request content, they get it from the nearest node rather than from the origin server. This reduces latency and origin server bandwidth pressure.

ByteDance has built its own CDN network, deploying hundreds of thousands of edge nodes globally. This allows it to provide smooth video services at relatively low cost.

---

Winter 2019. I was waiting for a friend on a street in San Francisco. A teenage girl sat on a bench, the screen glowing harshly in the dark. She stared at TikTok, her finger mechanically swiping upward, not looking up for a full twenty minutes. I watched her and suddenly realized: the algorithm had already won.

Summer 2018. I downloaded Douyin for the first time on the Beijing subway. I planned to browse casually, but one station, two stations, three stations passed, and my finger was still mechanically swiping upward. Each one was only 15 seconds, but each was like a hook—you don't know what the next one is, but you can't help but want to see. When I looked up, at least half the people in the carriage were looking down, screens showing the same vertical video stream. At that moment, I realized: this is not entertainment; this is a carefully designed attention harvest. You are kidnapped.

In 2017, Douyin was just starting, and users were mainly young people.

Download the app, scroll through a few videos, and find you can't stop—this was the common experience of many users at the time. Videos were short, only 15 seconds. Each was carefully designed to grab attention. You don't know what the next one is, but you can't help but want to see.

This is a war for attention.

Everyone's time is limited. There are only 24 hours in a day; excluding work and sleep, there are only a few hours available for entertainment. Whoever occupies this time gains commercial value.

ByteDance is the winner of this war. Toutiao, Douyin, TikTok occupy the time of billions of users globally. Users spend hours on these apps every day, watching ads and contributing revenue.

But this war also has a cost.

Users are addicted to short videos, unable to focus on deep reading and thinking. Teenagers spend large amounts of time on TikTok, affecting study and social life. Public opinion is shaped by algorithms; extreme views spread more easily.

Algorithms are not neutral.

Algorithm designers determine algorithm goals. If the goal is to maximize user dwell time, algorithms will recommend addictive content. If the goal is to maximize ad revenue, algorithms will recommend content that easily triggers clicks.

ByteDance's algorithm goal is "user value," but what is the definition of "user value"? Is it users' long-term well-being or users' short-term dwell time?

This is an ethical question. Tech companies need to think: are we creating value for users or extracting value from users?

---

**Epilogue: March 23, 2023**

US Congressional Hearing.

TikTok CEO Shou Zi Chew stood before members of Congress, answering questions about data security, content moderation, and Chinese influence.

The members' questions were sharp and repetitive. Chew's answers were cautious and standard.

This hearing lasted five hours. It didn't change anything, but it symbolized an era: Chinese internet companies have become protagonists on the global stage, and their every move is under scrutiny.

TikTok's fate remains uncertain. It may be banned, it may be sold, it may continue to operate.

But one thing is certain: the war for attention will continue. Algorithms will continue to feed content, and users will continue to scroll.

The only question is: who will control the algorithms?

The destiny of code depends on the people holding the keyboard.

And the next chapter of the story has just begun.