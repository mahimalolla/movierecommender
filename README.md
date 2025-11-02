#  Adaptive AI Entertainment Recommender

###  A GenAI + Meta-Learning-powered Cross-Domain Recommendation System    
*(Northeastern University)*

---

##  1. Problem Statement

Current entertainment platforms (Netflix, Spotify, Steam, Goodreads, etc.) rely heavily on traditional recommendation algorithms that:
- Perform poorly for **new users with limited data** (cold-start problem)  
- Operate in **isolated domains** (movies only, or music only)  
- Lack **contextual understanding** of user intent and trends  

Our project solves these challenges by building an **adaptive, cross-domain recommendation platform** that uses:
- **Meta-Learning (Few-Shot Learning):** to learn each user’s taste from minimal interactions  
- **Generative AI:** to interpret natural-language queries and explain recommendations conversationally  
- **Cross-Domain Graphs:** linking movies, music, books, and games for broader discovery  
- **Real-Time Trend Overlays:** blending personal recommendations with global & local popularity signals  

 **Goal:** Deliver a personalized, explainable, and production-ready entertainment recommender that evolves with both the **user’s preferences** and **global trends**.

---

##  2. System Architecture — Four Core Components

###  **1. Meta-Learning Personalization**
- Addresses the cold-start problem using few-shot learning.
- Rapidly adapts to new users with fewer than 10 ratings.
- Combines collaborative and content-based features with an XGBoost baseline.
- Learns user embeddings that update dynamically as new preferences appear.

###  **2. Generative AI Conversational Layer**
- Built with a lightweight LLM interface (Gemini API).  
- Users can type natural queries like:
  > “I want something like *Interstellar* but shorter and more cheerful.”
- The model parses the query → identifies intent (genre, tone, length) → calls the recommender → generates an **explanation** for transparency.  

###  **3. Cross-Domain Recommendation Network**
- Connects multiple media ecosystems (Movies , Music , Books , Games).  
- Builds a unified **vector embedding space** using Sentence-Transformers.  
- Integrates data from APIs: TMDB (movies), Spotify (music), Goodreads (books), Steam (games).  
- Suggests thematically related content — e.g., liking *Interstellar* may recommend *Dune* (book), *Hans Zimmer’s soundtrack*, or *Foundation* (series).

###  **4. Real-Time Global Trend Overlay**
- Fetches trending content from sources like **Netflix Top 10**, **Spotify Viral 50**, **Steam Top Sellers**, and **YouTube Trending**.  
- Merges personal and trend scores:
