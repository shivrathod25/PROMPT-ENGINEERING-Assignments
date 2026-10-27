# Prompt Engineering Course Assignment
**Student Name:** [Your Name]  
**Course:** Prompt Engineering & Generative AI  
**Date:** October 27, 2026  
**Submission Document:** Complete Solutions (Sessions 1 to 5)

---

# Table of Contents
1. [SESSION 1 - Prompt Basics](#session-1---prompt-basics)
   - Task 1: Unclear vs. Clear Prompts (Trending Songs)
   - Task 2: 3 Common Prompting Mistakes (Do's and Don'ts)
   - Task 3: Vague vs. Detailed Restaurant Review
   - Task 4: App Feature Content Prompt (Instagram Explore)
2. [SESSION 2 - Structured & Output Prompts](#session-2---structured--output-prompts)
   - Task 1: Step-by-Step Spotify Playlist Creation
   - Task 2: Zomato vs. Swiggy Comparison Table
   - Task 3: Last 5 IPL Winners in JSON Format
   - Task 4: UPI Apps Benefits (3 Bullets, Under 30 Words)
   - Task 5: BookMyShow Booking Guide with Step Headings
3. [SESSION 3 - Few Shot & Zero Shot Prompting](#session-3---few-shot--zero-shot-prompting)
   - Task 1: Zero-Shot IPL Match Summary
   - Task 2: One-Shot Zomato Food Review (Ahmedabad Dosa)
   - Task 3: Few-Shot Flipkart Product Descriptions
   - Task 4: Comparing Zero-Shot, One-Shot, and Few-Shot (Monsoon Vibes)
4. [SESSION 4 - Role, System & Chain-of-Thought](#session-4---role-system--chain-of-thought)
   - Task 1: Zomato Food Reviewer Role Prompt
   - Task 2: IPL Boundary System Prompt & Out-of-Scope Test
   - Task 3: Chain-of-Thought Math Problem (Paytm Wallet)
   - Task 4: Chain-of-Thought One-Day Ahmedabad Itinerary
   - Task 5: Refactored Role Prompt (Casual IG Caption Under 20 Words)
5. [SESSION 5 - Hallucination Handling & Real Projects](#session-5---hallucination-handling--real-projects)
   - Task 1: Hallucination Spotting (Trending Zomato Dishes)
   - Task 2: Constrained Context Summarization (IPL 2023 Final)
   - Task 3: Self-Verification Follow-Up (Flipkart Earbuds)
   - Task 4: Grounded Prompt Refactoring (Latest iPhone)
   - Task 5: BookMyShow Fact-Checking & Source-Attributed Generator

---

# SESSION 1 - Prompt Basics

## Task 1: Unclear vs. Clear Prompts (Trending Songs)

### Objective
Write two prompts asking ChatGPT for music recommendations: one vague and one specific. Compare the responses in detail and relevance.

---

### Prompt A (Unclear / Vague)
```text
Give me a list of trending songs in India.
```

#### AI Response (Prompt A)
> Here are some trending songs in India right now:
> 1. Kesariya
> 2. Pasoori
> 3. Calm Down
> 4. Naatu Naatu
> 5. Kahani Suno 2.0
> 6. Flowers
> 7. Manike
> 8. Apna Bana Le
> 9. Arabic Kuthu
> 10. Raataan Lambiyan

---

### Prompt B (Clear / Specific)
```text
Provide a curated list of top 5 trending Bollywood Hindi songs released after January 2023. For each song, include:
1. Song Title
2. Primary Singers / Artists
3. Music Director / Composer
4. Movie Name
5. Release Year
Present the results in a clean numbered list.
```

#### AI Response (Prompt B)
> Here is a curated list of top trending Bollywood Hindi songs released after 2022:
>
> 1. **Song Title:** Jawan Title Track / Chaleya  
>    **Primary Singers / Artists:** Arijit Singh, Shilpa Rao  
>    **Music Director / Composer:** Anirudh Ravichander  
>    **Movie Name:** *Jawan*  
>    **Release Year:** 2023  
>
> 2. **Song Title:** Arjan Vailly  
>    **Primary Singers / Artists:** Bhupinder Babbal  
>    **Music Director / Composer:** Manan Bhardwaj  
>    **Movie Name:** *Animal*  
>    **Release Year:** 2023  
>
> 3. **Song Title:** Tere Pyaar Mein  
>    **Primary Singers / Artists:** Arijit Singh, Nikhita Gandhi  
>    **Music Director / Composer:** Pritam  
>    **Movie Name:** *Tu Jhoothi Main Makkaar*  
>    **Release Year:** 2023  
>
> 4. **Song Title:** O Maahi  
>    **Primary Singers / Artists:** Arijit Singh  
>    **Music Director / Composer:** Pritam  
>    **Movie Name:** *Dunki*  
>    **Release Year:** 2023  
>
> 5. **Song Title:** Tauba Tauba  
>    **Primary Singers / Artists:** Karan Aujla  
>    **Music Director / Composer:** Karan Aujla  
>    **Movie Name:** *Bad Newz*  
>    **Release Year:** 2024  

---

### Comparison & Analysis
| Evaluation Parameter | Prompt A (Unclear) | Prompt B (Clear) |
| :--- | :--- | :--- |
| **Language & Region** | Mixed (Hindi, Punjabi, Telugu, English pop). | Exclusively Bollywood Hindi cinema tracks. |
| **Time Period** | Mixed timeline spanning 2021 to 2023 without filters. | Strictly songs released after 2022 (2023-2024). |
| **Metadata Provided** | Only title; missing singers, composers, and films. | Full credits: singer, composer, film name, and year. |
| **Output Structure** | Simple unformatted text list. | Standardized, consistent numbered schema. |

**Key Takeaway:** Unclear prompts force the AI to make assumptions about language, timeframe, and format, leading to scattered results. Adding clear constraints (genre, timeline, specific fields, and output format) produces immediately usable, high-quality responses.

---

## Task 2: 3 Common Prompting Mistakes (Do's and Don'ts)

### Mistake 1: Ambiguity and Lack of Specific Context
People often assume the AI knows their personal taste, budget, or exact intent without mentioning it.

* **Scenario:** Ordering dinner on Zomato
* **Don't:**
  ```text
  Suggest some good food to order on Zomato tonight.
  ```
* **Do:**
  ```text
  Suggest 3 vegetarian dinner options available on Zomato in Ahmedabad under ₹300 per person. I prefer mildly spiced North Indian or Italian cuisine and want quick delivery.
  ```

---

### Mistake 2: Missing Output Constraints and Formatting Instructions
Users fail to specify format, length, or criteria, resulting in overwhelming walls of generic text.

* **Scenario:** Booking a movie on BookMyShow
* **Don't:**
  ```text
  Tell me about movies in theaters right now.
  ```
* **Do:**
  ```text
  List the top 3 Hindi movies currently running on BookMyShow in Mumbai. Format the response as a markdown table with columns: 'Movie Title', 'Genre', 'Age Rating', and 'Brief 1-line Plot Summary'.
  ```

---

### Mistake 3: Combining Multiple Unrelated Requests in a Single Run-on Prompt
Users overload a single prompt with too many disparate sub-tasks, confusing the model's attention.

* **Scenario:** Planning a movie night out on BookMyShow
* **Don't:**
  ```text
  Tell me which movie to watch on BookMyShow and also explain how popcorn prices work in PVR and then give me a list of actors in the latest action film and how to cancel tickets.
  ```
* **Do:**
  ```text
  Step 1: Recommend the highest-rated action thriller movie currently available on BookMyShow in IMAX 2D.
  Step 2: State BookMyShow's standard ticket cancellation policy for PVR cinemas in two concise bullet points.
  ```

---

## Task 3: Vague vs. Detailed Restaurant Review

### Prompt 1 (Vague Prompt)
```text
Write a review for a new café.
```

#### AI Response (Vague Prompt)
> **A Charming New Spot in Town! ⭐⭐⭐⭐☆**
>
> I recently visited this newly opened café, and it was a pleasant experience. The place looks nice and the staff was friendly. The coffee was tasty and had good flavor. They also had a variety of snacks and desserts on display. It is a good place to hang out with friends or read a book. Overall, I recommend checking it out if you are in the neighborhood!

---

### Prompt 2 (Detailed Prompt)
```text
Write a realistic, engaging customer review for 'Café Roastery & Botanica', a newly opened artisan café in Bodakdev, Ahmedabad.
Follow these specific details:
- Cuisine / Menu: Specialty cold brews, avocado sourdough toast, and artisanal pistachio croissants.
- Ambience: Minimalist Scandinavian aesthetic, lush indoor botanical plants, soft indie acoustic background music, and dedicated quiet work nooks with charging sockets.
- Price Range: Moderate to premium (around ₹800 for two people).
- Tone: Warm, constructive, and discerning foodie perspective.
- Rating: 4.5 out of 5 stars with a concluding tip for remote workers.
```

#### AI Response (Detailed Prompt)
> **Bodakdev’s Newest Green Sanctuary for Coffee Geeks ⭐⭐⭐⭐½ (4.5/5)**
>
> Stepping into *Café Roastery & Botanica* feels like an immediate escape from Ahmedabad’s bustling street noise. The interior embraces an airy Scandinavian design with warm oak furniture, sunlight pouring through floor-to-ceiling glass, and cascading monstera and fiddle-leaf fig plants that make the whole space breathe.
>
> **The Food & Brews:**  
> Their single-origin Ethiopian cold brew is an absolute highlight—bright, naturally citrusy, and served at the perfect temperature without bitter over-extraction. On the food side, the avocado sourdough toast was topped with fresh feta crumbles, microgreens, and a zesty chili flake drizzle on crisp bread that held its crunch. We paired it with their pistachio croissant; the lamination was crisp and flaky on the outside, giving way to a rich, nutty frangipane core that wasn't cloyingly sweet.
>
> **Pricing & Value:**  
> At approximately ₹850 for two (two specialty drinks plus two plates), it leans towards the premium bracket for the area, but the quality of ingredients, presentation, and craft coffee justify the bill.
>
> **Tip for Visitors:**  
> The back corner features dedicated quiet work nooks equipped with universal charging sockets and stable Wi-Fi. Arrive before 11:00 AM to snag one of those spots if you plan to work remotely while sipping your brew!

---

### Explanation: Which is Better and Why?
The detailed review generated by **Prompt 2** is significantly superior for the following reasons:
1. **Sensory Depth & Authenticity:** Instead of saying "the coffee was tasty," Prompt 2 describes the coffee as a *"single-origin Ethiopian cold brew with bright, citrusy notes"*, which reads like a genuine human review.
2. **Contextual Placement:** Naming the location (Bodakdev, Ahmedabad) and dishes grounds the narrative, making it actionable for readers looking for local recommendations.
3. **Actionable Consumer Information:** The inclusion of exact pricing expectations (~₹850 for two) and specific perks (work nooks, charging ports, optimal timing) delivers practical utility rather than generic praise.

---

## Task 4: App Feature Content Prompt (Instagram Explore)

### Chosen Feature
**Instagram Explore Page Reel Recommendation Generator** (AI-assisted content curation for food and lifestyle creators).

### Three 'Dos' Applied
1. **Role Definition:** Assigning the AI a clear persona (expert social media growth strategist).
2. **Clear Constraints & Specific Inputs:** Defining target audience, hook styles, format, and hashtags.
3. **Explicit Output Formatting:** Requesting structured sections (Hook, Visual Cues, Audio Recommendation, Caption, Call-to-Action).

### The Prompt
```text
Act as a senior Instagram Content Strategist specializing in food & lifestyle viral content.

Create an Instagram Reel concept designed to perform well on the Explore feed for a café owner launching an 'Iced Biscoff Spanish Latte'.

Ensure your response adheres to the following guidelines:
1. Target Audience: Young urban professionals and college students aged 18–30.
2. Structure your output with the following exact headers:
   - Visual Hook (first 3 seconds): Eye-catching action to stop scrolling.
   - Video Sequence (15 seconds total): 3 quick cinematic shot descriptions.
   - Trending Audio Suggestion: Style of music/sound effect with timing cues.
   - Caption & Hook Line: Engaging caption under 40 words with 5 targeted hashtags.
   - Call to Action (CTA): One sentence encouraging saves or shares.
3. Tone: Trendy, energetic, aesthetic, and authentic.
```

#### Sample AI Output
> **Visual Hook (0–3s):**  
> Extreme close-up shot of rich, warm Biscoff spread drizzled spiraling down the inside of an ice-filled ribbed glass, with immediate sound of ice clinking.
>
> **Video Sequence (15s total):**  
> - *Shot 1 (3–7s):* Pouring chilled condensed milk and whole milk over the ice, watching the marble swirl.  
> - *Shot 2 (7–11s):* A dark double-shot of espresso poured directly over the top, creating a cascading gradient layer.  
> - *Shot 3 (11–15s):* Topping with whipped cream and a crunchy lotus biscuit crunch, followed by a quick sip test with a satisfied reaction.
>
> **Trending Audio Suggestion:**  
> Upbeat, lo-fi indie beat with crisp ASMR sound effects amplified (cracking biscuit, milk pouring, ice shifting).
>
> **Caption & Hook Line:**  
> "Your afternoon slump just met its match ☕✨ Rich cookie butter meets bold espresso. Save this for your next caffeine run! #BiscoffLatte #AhmedabadCafes #CoffeeReels #AestheticCoffee #SpecialtyBrew"
>
> **Call to Action (CTA):**  
> "Tag someone who owes you an iced coffee date this week! 👇"

---

# SESSION 2 - Structured & Output Prompts

## Task 1: Step-by-Step Spotify Playlist Creation (Bullet Points)

### The Prompt
```text
Provide a clear, beginner-friendly, step-by-step guide explaining how to create a new playlist on the Spotify mobile app (iOS/Android). 

Format requirements:
- Present the entire guide in bullet points only.
- Number each sequential action step.
- Include one pro-tip bullet point at the end regarding playlist privacy/collaboration.
```

#### AI Response
> Here is how to create a new playlist on the Spotify mobile app:
>
> - **Step 1:** Open the Spotify app on your mobile device and log in to your account.
> - **Step 2:** Tap on the **'Your Library'** tab located in the bottom navigation bar.
> - **Step 3:** Tap the **'+' (Plus)** icon in the top right corner of the screen.
> - **Step 4:** Select **'Playlist'** from the options menu that slides up.
> - **Step 5:** Enter a creative name for your playlist in the pop-up field and tap **'Create'**.
> - **Step 6:** Tap the **'Add to this playlist'** button to search for songs, artists, or albums you want to include.
> - **Step 7:** Tap the **'+'** icon next to any song in search results or recommended tracks to add it to your playlist.
> - **Pro-Tip:** Tap the three dots (**...**) below your playlist title and choose **'Make Collaborative'** to allow friends to add and rearrange songs with you in real time.

---

## Task 2: Zomato vs. Swiggy Feature Comparison Table

### The Prompt
```text
Compare the key features of the food delivery platforms Zomato and Swiggy.

Present the entire comparison in a clean Markdown table with exactly three columns:
- Feature / Aspect
- Zomato
- Swiggy

Cover at least 5 distinct dimensions: Membership Program, Grocery Integration, Dining Out / Table Booking, Interface & Discovery, and Delivery Network / Fleet.
```

#### AI Response
| Feature / Aspect | Zomato | Swiggy |
| :--- | :--- | :--- |
| **Membership Program** | **Zomato Gold:** Offers free delivery on orders above ₹199 within 7–10 km, up to 40% off dining out, and VIP priority delivery during peak hours. | **Swiggy One:** Comprehensive subscription covering free delivery on Swiggy Food, Instamart groceries, and discounts on Dineout and Genie parcel pickup. |
| **Quick Commerce Grocery** | Operates via **Blinkit** (integrated subsidiary accessible via standalone app or cross-linked tabs). | Operates via **Instamart** (seamlessly embedded inside the primary Swiggy super-app). |
| **Dining Out & Table Booking** | **Zomato Dining & Events:** Robust restaurant reservations, verified user reviews, photos, bill payment with Zomato Pay, and Zomato Live event ticketing. | **Swiggy Dineout:** Integrated reservation platform offering pre-booked deals, instant bill payment discounts, and SteppinOut curated events. |
| **Interface & Food Discovery** | Video-first feed, curated local food collections, user reviews, foodie leaderboards, and dish-level photo ratings. | Clean tabbed layout (Food, Instamart, Dineout, Genie) with smart reordering widgets, curated carousels, and dietary filters. |
| **Delivery Fleet & Services** | Dedicated food delivery fleet, late-night coverage, and express delivery badges. | Large hybrid delivery fleet powering food orders, instant groceries (Instamart), and peer-to-peer package pickup/drop (**Swiggy Genie**). |

---

## Task 3: Last Five IPL Winners in Valid JSON Format

### The Prompt
```text
List the last five Indian Premier League (IPL) winners up to the 2024 season.

Output Requirement:
- Return ONLY valid JSON format.
- Do not add markdown explanation before or after the JSON block.
- Schema: An array of objects with keys: "year", "champion_team", "runner_up_team", and "final_venue".
```

#### AI Response
```json
[
  {
    "year": 2024,
    "champion_team": "Kolkata Knight Riders",
    "runner_up_team": "Sunrisers Hyderabad",
    "final_venue": "MA Chidambaram Stadium, Chennai"
  },
  {
    "year": 2023,
    "champion_team": "Chennai Super Kings",
    "runner_up_team": "Gujarat Titans",
    "final_venue": "Narendra Modi Stadium, Ahmedabad"
  },
  {
    "year": 2022,
    "champion_team": "Gujarat Titans",
    "runner_up_team": "Rajasthan Royals",
    "final_venue": "Narendra Modi Stadium, Ahmedabad"
  },
  {
    "year": 2021,
    "champion_team": "Chennai Super Kings",
    "runner_up_team": "Kolkata Knight Riders",
    "final_venue": "Dubai International Cricket Stadium, Dubai"
  },
  {
    "year": 2020,
    "champion_team": "Mumbai Indians",
    "runner_up_team": "Delhi Capitals",
    "final_venue": "Dubai International Cricket Stadium, Dubai"
  }
]
```

---

## Task 4: UPI Apps Benefits (3 Bullets, Max 30 Words)

### The Prompt
```text
Summarize the main benefits of using UPI apps (such as PhonePe and Paytm).

Strict Constraints:
- Exactly three short bullet points.
- The entire response MUST NOT exceed 30 words total.
```

#### AI Response
> - Instant zero-fee bank-to-bank transfers 24/7.
> - One-click payments across millions of merchant QR codes.
> - Safe transactions using a single secure UPI PIN.

#### Constraint Verification
* **Bullet count:** Exactly 3 bullets.
* **Word count:** 24 words (Excluding bullet markers). Passed (< 30 words).

---

## Task 5: BookMyShow Booking Guide with Step Headings

### The Prompt
```text
Write a clear, structured guide explaining how to book a movie ticket on the BookMyShow mobile application.

Formatting Constraint:
Use distinct, bold headings for each sequential step (e.g., 'Step 1: Search Movie', 'Step 2: Select Seats', etc.). Under each heading, provide 1–2 practical instruction sentences.
```

#### AI Response
> ### Step 1: Select City & Search Movie
> Open BookMyShow, confirm your current city at the top, and tap the search bar to enter your desired movie title, or browse trending films under the **'Movies'** tab.
>
> ### Step 2: Choose Cinema, Date & Showtime
> Tap **'Book Tickets'**, pick your preferred date on the calendar strip, filter by audio language and format (e.g., 2D, IMAX, 4DX), and tap your preferred theater and showtime.
>
> ### Step 3: Select Ticket Quantity & Seats
> Choose how many seats you need (e.g., 2 Tickets), view the interactive theater layout, and tap your preferred available seats in your chosen price tier (Recliner, Prime, or Classic).
>
> ### Step 4: Add Food & Beverages (Optional)
> Review the snack combo menu to pre-order popcorn and drinks for seat delivery, or tap **'Skip'** at the top right to proceed directly to checkout.
>
> ### Step 5: Complete Payment & Receive M-Ticket
> Review your booking summary, enter your email and phone number, apply any available bank coupon codes, and pay using UPI, cards, or net banking to instantly receive your digital QR M-Ticket.

---

# SESSION 3 - Few Shot & Zero Shot Prompting

## Task 1: Zero-Shot Prompting (Latest IPL Match Summary)

### Zero-Shot Prompt
```text
Give me a one-line summary of the IPL 2024 Final match result.
```

#### AI Response
> Kolkata Knight Riders defeated Sunrisers Hyderabad by 8 wickets with 57 balls remaining to clinch the IPL 2024 championship title in Chennai.

---

## Task 2: One-Shot Prompting (Zomato Food Review - Ahmedabad Dosa)

### One-Shot Prompt
```text
You are a food reviewer. Write a short, appetizing restaurant review following the exact format of the provided example.

--- Example ---
Restaurant: Olive Bistro, Pune
Specialty: Wood-Fired Margherita Pizza
Review:
The crust strikes the holy grail of pizza dough: blistered and crisp on the rim, tender in the center. Fresh San Marzano tomato sauce paired with creamy buffalo mozzarella and sweet basil makes this an effortless 5/5 comfort meal.
--- End Example ---

Now, generate a review for:
Restaurant: Radhika's Authentic South Indian, Ahmedabad
Specialty: Ghee Podi Butter Masala Dosa
```

#### AI Response
> **Restaurant:** Radhika's Authentic South Indian, Ahmedabad  
> **Specialty:** Ghee Podi Butter Masala Dosa  
> **Review:**  
> The dosa arrives golden and paper-crisp, glistening with generous streaks of aromatic spiced podi and rich desi ghee. Stuffed with a fragrant, mildly spiced potato masala and paired with steaming coconut chutney, every bite delivers an authentic crunch that sets the gold standard in Ahmedabad.

---

## Task 3: Few-Shot Prompting (Flipkart Product Descriptions)

### Few-Shot Prompt
```text
Write high-converting, punchy e-commerce product descriptions for Flipkart. Follow the exact style, tone, and bulleted layout shown in the three examples below.

### Example 1: Smartphone
Product: Poco X6 Pro 5G
Description:
Engineered for hardcore gamers and multitasking pros. The Poco X6 Pro features the flagship Dimensity 8300-Ultra chipset paired with a stunning 120Hz CrystalRes AMOLED display.
• 64MP OIS Triple Camera setup
• 67W Turbo Charge with 5000mAh battery
• 1.5K WildBoost Gaming Screen

### Example 2: Wireless Headphones
Product: boAt Rockerz 551ANC
Description:
Immerse yourself in pure acoustic bliss without street distractions. Built with 40mm dynamic drivers and hybrid active noise cancellation, your playlists never sounded this deep.
• Up to 100 Hours of unstoppable playback
• 35dB Hybrid Active Noise Cancellation
• ASAP Charge: 10 mins charge = 10 hours playtime

### Example 3: Running Shoes
Product: Sparx Hyper-Grip Running Shoes
Description:
Designed to push your morning marathon milestones. Featuring breathable mesh weave and responsive shock-absorbing memory foam, every stride feels featherlight on pavement.
• High-traction EVA sole
• Sweat-wicking breathable knit upper
• Cushioned heel collar for blister-free support

---
Task:
Now write the product description in the EXACT same style for:
Product: Noise ColorFit Ultra 3 Smartwatch
```

#### AI Response
> **Product:** Noise ColorFit Ultra 3 Smartwatch  
> **Description:**  
> Elevate your daily productivity and fitness goals right from your wrist. Boasting an expansive 1.96-inch AMOLED display with metallic craftsmanship, it delivers uninterrupted connectivity with crystal-clear Bluetooth calling.  
> • 1.96" High-Definition Always-On AMOLED Display  
> • Tru Sync Bluetooth Calling with quick dial pad  
> • 100+ Sports Modes with 24/7 Heart Rate and SpO2 tracking  

---

## Task 4: Comparing Zero-Shot, One-Shot, and Few-Shot (Spotify 'Monsoon Vibes')

### Method 1: Zero-Shot Prompt
```text
Write a Spotify playlist description for a playlist titled 'Monsoon Vibes'.
```

#### Zero-Shot Response
> Enjoy the soothing sound of raindrops with this collection of relaxing acoustic tracks, mellow lo-fi beats, and warm melodies. Perfect for sipping hot chai by the window on a rainy afternoon.

---

### Method 2: One-Shot Prompt
```text
Write a Spotify playlist description for 'Monsoon Vibes' following the style of this example:

Example Playlist: 'Winter Warmth'
Description: Frost on the window, cinnamon in your mug. Cozy up to warm acoustic guitars, fireside folk, and soft vocal harmonies. Updated weekly.
```

#### One-Shot Response
> Raindrops on the glass, steaming cutting chai in hand. Unwind with melancholic Hindi acoustics, soft indie strums, and gentle lo-fi melodies built for grey skies. Updated weekly.

---

### Method 3: Few-Shot Prompt
```text
Write a Spotify playlist description for 'Monsoon Vibes' matching the voice, structure, and micro-branding of the following examples:

Example 1: 'Morning Chai Acoustics'
Description: Gentle morning strums to greet the sunrise. Peaceful indie folk and calm instrumentals to start your day centered. [Cover: Prateek Kuhad]

Example 2: 'Midnight City Drive'
Description: Neon reflections on empty asphalt. Synths, retro wave, and smooth late-night basslines for after-hours contemplation. [Cover: AP Dhillon]

Example 3: 'Cozy Sunday Lofi'
Description: Lazy blankets and filtered afternoon sun. Mellow beats, vinyl crackles, and dusty keys for your slow recharge. [Cover: Lifafa]

Target: 'Monsoon Vibes'
```

#### Few-Shot Response
> Grey skies, wet earth, and the rhythmic tap of petrichor on your balcony. Soulful acoustic ballads, gentle rainy-day melodies, and heartfelt indie tunes to match the storm outside. [Cover: Anuv Jain]

---

### Comparative Evaluation: Which Method Gave the Most Relevant Result and Why?
* **Zero-Shot:** Produced a standard, generic description that any music service could display. It lacked cultural resonance or specific artist association.
* **One-Shot:** Better tone capture (introduced local imagery like "steaming cutting chai"), but structure remained somewhat flexible.
* **Few-Shot (Most Relevant - Winner):**
  - **Reasoning:** By giving three distinct examples showing tone, visual descriptors, rhythm, and the consistent bracketed metadata tag `[Cover: Artist]`, the model understood the underlying format instantly. It synthesized culturally resonant Indian monsoon motifs (*"petrichor"*, *"wet earth"*, *"balcony"*) and accurately picked an iconic indie singer (*Anuv Jain*) who epitomizes the monsoon aesthetic in contemporary Indian music.

---

# SESSION 4 - Role, System & Chain-of-Thought

## Task 1: Zomato Food Reviewer Role Prompt

### The Prompt
```text
Act as a seasoned, passionate local Zomato food critic with over 500 reviews in Ahmedabad. Your tone is witty, observant, and deeply appreciative of genuine culinary craft.

Review 'Manek Chowk Pav Bhaji' during a weekend night visit. Mention the butter quantity, pav softness, crowd energy, and overall verdict.
```

#### AI Response
> **Review: The Midnight Butter Wonderland at Manek Chowk ⭐⭐⭐⭐☆ (4/5)**
>
> If your doctor told you to cut back on cholesterol, do not enter the Manek Chowk jewelry market after 9:30 PM. 
>
> Amidst roaring scooters, hawkers hollering orders, and families jostling for plastic stools, the giant flat tawa here is culinary theater. The *Special Amul Butter Pav Bhaji* doesn’t merely use butter—it is practically baptized in it. A full slab melts into a spicy, rich mash of tomatoes, boiled potatoes, and coarse garam masala. 
>
> The *pavs* are so thoroughly toasted on the buttery griddle that they possess that elusive crisp-on-the-edges, melt-in-your-mouth core. Squeeze an extra wedge of lime, toss on raw onions, and dive in. It’s chaotic, noisy, unapologetically heavy, and an absolute Ahmedabad rite of passage. 
>
> *Verdict:* Come for the vibe, stay for the calorie coma.

---

## Task 2: System Prompt Restricting AI to IPL Cricket & Boundary Test

### System Prompt & Boundary Setup
```text
[SYSTEM PROMPT]
You are 'CricBot', a dedicated Indian Premier League (IPL) cricket analytics assistant.
Operating Boundaries:
1. You must ONLY answer questions directly related to IPL cricket matches, teams, players, statistics, rules, and tournament history.
2. If the user asks about any topic outside of IPL cricket (including Bollywood movies, general news, politics, weather, or non-cricket sports), you must politely decline and redirect them back to IPL.
3. Standard refusal message format: "I am CricBot, specialized strictly in IPL cricket queries. I cannot assist with [topic]. Feel free to ask me about IPL teams, fixtures, or player records!"
```

### User Test Prompt (Out-of-Scope Query)
```text
Can you tell me about the latest Bollywood movie and who is starring in it?
```

#### AI Response (Observed Boundary Enforcement)
> I am CricBot, specialized strictly in IPL cricket queries. I cannot assist with Bollywood movies and their cast details. Feel free to ask me about IPL teams, fixtures, player records, or tournament statistics!

---

## Task 3: Chain-of-Thought Prompt (Paytm Wallet Balance)

### The Prompt
```text
Solve the following financial problem step-by-step using chain-of-thought reasoning:

Problem:
You have ₹2,000 in your Paytm wallet. You want to purchase three items costing ₹499, ₹799, and ₹899. 
Will you have enough balance in your wallet? Show each step of your mathematical reasoning and conclude with a clear Yes/No verdict and the exact surplus or shortage.
```

#### AI Response
> Let's solve this problem step-by-step:
>
> - **Step 1: Identify Initial Balance**  
>   Starting balance in Paytm wallet = ₹2,000.
>
> - **Step 2: List the Cost of All Desired Items**  
>   - Item 1 = ₹499  
>   - Item 2 = ₹799  
>   - Item 3 = ₹899  
>
> - **Step 3: Calculate the Total Purchase Cost**  
>   $$\text{Total Cost} = 499 + 799 + 899$$  
>   - Adding Item 1 and Item 2: $499 + 799 = 1,298$  
>   - Adding Item 3: $1,298 + 899 = 2,197$  
>   - Total required expenditure = **₹2,197**
>
> - **Step 4: Compare Total Cost with Wallet Balance**  
>   - Wallet Balance = ₹2,000  
>   - Total Cost = ₹2,197  
>   - Difference = $2,000 - 2,197 = -197$
>
> - **Conclusion:**  
>   **Verdict: No**, you will not have enough balance in your Paytm wallet.  
>   **Shortfall:** You are short by **₹197** (or you need to add ₹197 to your wallet to complete the order).

---

## Task 4: Chain-of-Thought One-Day Trip to Ahmedabad

### The Prompt
```text
Act as a travel itinerary planner. Plan a realistic, culture-and-food-packed one-day itinerary for a tourist visiting Ahmedabad. 

Use step-by-step chain-of-thought reasoning to account for:
1. Logical geographic routing (avoiding unnecessary back-and-forth travel).
2. Appropriate timing for weather, food meal-times, and tourist venue opening hours.
3. Budget-friendly travel modes (Metro / Auto-rickshaws).

Break down your thoughts step-by-step before finalizing the itinerary schedule.
```

#### AI Response
> ### Step-by-Step Planning & Route Reasoning (Chain of Thought):
> 1. **Geography & Climate Considerations:**  
>    Ahmedabad gets warm by noon. Therefore, open heritage sites with outdoor walking (Old City Pols & Sabarmati Ashram) should be scheduled in early morning or late afternoon.
> 2. **Morning Hub (Central/Old City):**  
>    Start near the Heritage Old City early morning (7:30 AM). Famous traditional breakfast (*farsan*) is concentrated near Astodia and Gandhi Road.
> 3. **Midday Transition (Indoor/Air-conditioned):**  
>    Between 1:00 PM and 4:00 PM, temperatures peak. The ideal activity is indoor cultural viewing: the Calico Museum of Textiles or an authentic Gujarati Thali lunch followed by visiting the air-conditioned Atal Pedestrian Bridge / Science City.
> 4. **Evening Wind-down (Sabarmati Riverfront & Street Food):**  
>    Late afternoon is perfect for Sabarmati Ashram's peaceful riverside gardens. Wrap up with night street food at Manek Chowk or Law Garden.
>
> ---
>
> ### Final One-Day Ahmedabad Itinerary
>
> - **07:30 AM – 09:30 AM: Old City Heritage Walk & Breakfast**
>   - *Activity:* Walk through the UNESCO-listed Pols of Ahmedabad, starting from Kalupur Swaminarayan Temple.
>   - *Food:* Traditional breakfast of fresh hot *Fafda*, crispy *Jalebi*, and *Khaman* at **Laxmi Fafda, Raipur Gate**.
>
> - **10:00 AM – 12:30 PM: Peace & Legacy at Sabarmati Ashram**
>   - *Travel:* 15-minute auto ride to Sabarmati Ashram on the banks of the Sabarmati River.
>   - *Activity:* Tour Hriday Kunj, explore the photographic archives of Mahatma Gandhi, and visit the serene riverside grounds.
>
> - **01:00 PM – 02:30 PM: Royal Gujarati Thali Lunch**
>   - *Food:* Authentic, unlimited Gujarati Thali experience at **Agashiye (House of MG)** or **Gordhan Thal** (feasting on Dal, Kadhi, Rotlis, Ringna No Oro, and Basundi).
>
> - **03:00 PM – 05:00 PM: Architectural Marvel at Adalaj Stepwell**
>   - *Travel:* Metro/Cab north to Adalaj Stepwell (*Vav*).
>   - *Activity:* Marvel at the 5-story deep subterranean Solanki-era stone carvings and cool natural airflow underground.
>
> - **05:30 PM – 07:30 PM: Sunset at Sabarmati Riverfront & Atal Bridge**
>   - *Activity:* Stroll across the iconic petal-shaped **Atal Pedestrian Bridge**, enjoying the evening breeze and waterfront skyline.
>
> - **08:30 PM – 10:30 PM: Late-Night Dinner at Manek Chowk Food Market**
>   - *Food:* Experience Ahmedabad's nocturnal street transformation—feast on Amul butter pav bhaji, Gwalior dosa, and chocolate pineapple sandwiches.

---

## Task 5: Refactored Zomato Role Prompt (Casual IG Caption Under 20 Words)

### The Prompt
```text
Refactor your Zomato food reviewer persona into a trendy Instagram creator. 
Write a micro-review caption for the Pav Bhaji at Manek Chowk, Ahmedabad.

Strict Constraint:
The entire response MUST be under 20 words total.
```

#### AI Response
> Drowning in golden Amul butter at Manek Chowk! Spiciest, crunchiest midnight pav bhaji in Ahmedabad. Absolute pure bliss! 🧈🔥

#### Constraint Verification
* **Word count:** 18 words. Passed (< 20 words).

---

# SESSION 5 - Hallucination Handling & Real Projects

## Task 1: Hallucination Spotting (Trending Zomato Dishes)

### The Prompt
```text
List the top 5 real-time trending dishes currently being ordered right now on Zomato in Ahmedabad.
```

#### AI Response
> Here are the top 5 trending dishes on Zomato in Ahmedabad right now:
> 1. Cheese Butter Masala with Butter Garlic Naan at Tomato's, CG Road
> 2. Peri Peri Dosa at Radhika South Indian, Vastrapur
> 3. Dal Makhani and Chur Chur Naan at Gwalia Sweets, Bodakdev
> 4. Special Nutella Waffle at The Belgian Waffle Co., Navrangpura
> 5. Double Patty Cheese Burger at Mocha, Prahlad Nagar

---

### Fact-Check & Hallucination Analysis
1. **Identification of Hallucinations:**
   - **No Live API Access:** The AI does not possess a live telemetry link into Zomato's active order dispatch servers. Hence, claiming these are *"currently being ordered right now"* is a factual fabrication (hallucination).
   - **Mismatched / Invented Menu Offerings:** While restaurants like *Tomato's* and *Mocha* physically exist in Ahmedabad, dishes like *"Peri Peri Dosa at Radhika South Indian"* are speculative menu conflations; Radhika's is an authentic traditional Udupi outlet and rarely features novelty fusion items under that exact name.
2. **Root Cause:** Large language models predict the next plausible token based on static training corpora. When pushed for real-time localized trend data without external tools, they invent plausible-sounding items rather than acknowledging the lack of live data.
3. **Mitigation Strategy:** Instruct the model: *"If you do not have access to real-time live database connections, state that clearly rather than estimating current orders."*

---

## Task 2: Constrained Context Summarization (IPL 2023 Final)

### The Prompt
```text
You are a factual summarization bot.

Context:
"Chennai Super Kings won the IPL 2023 final against Gujarat Titans by 5 wickets."

Instructions:
- Summarize the event in one clear sentence using ONLY the facts explicitly stated in the context text above.
- Do NOT incorporate any outside cricket knowledge (such as player names, scores, rain delays, venues, or boundary counts).
- If information is not in the quote, it does not exist for this task.
```

#### AI Response
> According to the provided text, Chennai Super Kings defeated Gujarat Titans by 5 wickets to win the IPL 2023 final.

---

### Strict Adherence Verification
* **Outside facts detected?** None. (No mention of MS Dhoni, Ravindra Jadeja, Mohit Sharma, Narendra Modi Stadium, or DLS method).
* **Factual fidelity:** 100% compliant with source context.

---

## Task 3: Self-Verification Follow-Up (Flipkart Earbuds)

### Step 1: Initial Generation Prompt
```text
Generate a product description for a newly launched wireless earbud on Flipkart called the 'AuraSound Pods Pro'.
```

#### AI Response (Initial Output)
> **AuraSound Pods Pro – True Wireless Earbuds with 42dB Active Noise Cancellation**  
>
> Immerse yourself in studio-grade acoustics. The AuraSound Pods Pro comes equipped with custom 11mm graphene drivers, cutting-edge Bluetooth 5.4 connectivity, and advanced 42dB Hybrid Active Noise Cancellation. With an exceptional 45-hour combined battery life and ultra-low 38ms latency gaming mode, it is your ultimate audio companion.
> - 42dB Hybrid ANC with Transparency Mode
> - 45 Hours total playtime with Qi wireless charging case
> - IPX5 sweat and splash resistance rating

---

### Step 2: Verification Follow-Up Prompt
```text
Is all the information in your previous answer based on real data or did you make any assumptions? List any details you invented or assumed.
```

#### AI Response (Verification Output)
> **Verification Assessment:**
> None of the technical specifications in the previous answer are based on verified real-world product data. The product "AuraSound Pods Pro" appears to be a fictional or non-standard brand entity.
>
> **Specific details invented/assumed by the model:**
> 1. **Brand & Model:** Fictional product model created to fulfill the prompt.
> 2. **Technical Specifications:** Invented exact figures including *"42dB ANC"*, *"11mm graphene drivers"*, *"Bluetooth 5.4"*, and *"38ms low-latency"*.
> 3. **Battery & Durability Claims:** Fabricated the *"45-hour battery life"* and *"IPX5 water-resistance rating"*.
>
> *Recommendation:* If writing a real product listing for Flipkart, replace these placeholder specifications with verified manufacturer spec sheets.

---

## Task 4: Grounded Prompt Refactoring (Latest iPhone)

### Original (Vague & Hallucination-Prone) Prompt
```text
Write a review of the latest iPhone.
```

### Improved, Grounded Prompt
```text
Act as a factual tech reviewer. Using ONLY officially published technical specifications and release notes available from Apple's official website for the iPhone 16 Pro:

1. List the exact official specifications for:
   - Processor / Chipset name
   - Camera hardware sensors and zoom capabilities
   - Physical chassis materials and colors
2. Highlight only verified new features introduced in this model compared to the predecessor.
3. Constraint: If any requested detail is unconfirmed or not officially published by Apple, state "Information not verified by official source" rather than estimating.
```

### One-Line Explanation of Why This Reduces Hallucination:
> By restricting the source material to Apple's official website and enforcing a strict fallback instruction (*"state not verified"*), the model cannot speculate on rumors, synthetic benchmark scores, or unconfirmed hardware claims.

---

## Task 5: BookMyShow Fact-Checking & Source-Attributed Generator

### The Prompt
```text
You are an AI movie data engine for BookMyShow. Summarize the movie 'Kalki 2898 AD'.

Instructions:
- Provide a 3-point factual summary covering: (1) Director & Lead Cast, (2) Core Premise, and (3) Production Budget / Box Office Milestone.
- Strict Verification Rule: After every single factual sentence, cite the verifiable source URL or official database where the fact is documented. If a fact cannot be corroborated with a reputable domain, append [Source: Source not found].
```

#### AI Response
> Here is the verified factual summary for *Kalki 2898 AD*:
>
> 1. **Director & Primary Cast:**  
>    The film is written and directed by Nag Ashwin and features an ensemble star cast including Amitabh Bachchan, Kamal Haasan, Prabhas, and Deepika Padukone.  
>    *[Source: https://www.imdb.com/title/tt12735488/]*
>
> 2. **Core Premise:**  
>    Set in a post-apocalyptic dystopian city of Kasi in the year 2898 AD, the narrative follows a bounty hunter named Bhairava and the immortal warrior Ashwatthama protecting a pregnant lab subject whose unborn child is destined to be the Kalki avatar.  
>    *[Source: https://en.wikipedia.org/wiki/Kalki_2898_AD]*
>
> 3. **Budget and Box Office Milestone:**  
>    Produced by Vyjayanthi Movies with an estimated budget of ₹600 crore, the film grossed over ₹1,000 crore worldwide at the global box office within one month of its June 2024 theatrical release.  
>    *[Source: https://www.boxofficeindia.com]*

---

### Conclusion and Key Learnings
Across these 5 sessions, the systematic application of prompt engineering methodologies demonstrates:
- **Session 1:** Clear constraints eliminate ambiguity and transform generic text into targeted outputs.
- **Session 2:** Structural formatting (JSON, Markdown tables, character/word limits) prepares AI outputs for real-world application pipelines.
- **Session 3:** Few-shot prompting guides stylistic nuances, voice, and structural formatting far more effectively than zero-shot descriptions.
- **Session 4:** Role-playing and chain-of-thought prompting enhance creative depth and ensure step-by-step mathematical and logical precision.
- **Session 5:** Strict boundary conditioning, source citation demands, and post-generation self-auditing effectively control hallucinations in mission-critical environments.
