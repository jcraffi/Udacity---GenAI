# HomeMatch - A Personalized Real Estate Assistant

## Project Overview

### Introduction
This project, **HomeMatch**, is a personalized real estate recommendation system. It leverages **vector embeddings** and **semantic search** to match real estate listings to a buyer’s preferences, enhancing the home search process. 

I built this application using **GPT-4** to generate new real estate listings, AutoPipelineForText2Image, part of the **Hugging Face** Diffusers library to generate realistic property photos, **OpenAI's** clip-vit-large-patch14 for vector embeddings, **ChromaDB** for storage. OpenAI further tailored listings to unique prospective buys preferences. The goal was to provide **highly relevant listings** by understanding nuanced buyer preferences beyond simple filters.

This is part of Udacity's Generative Artificial Intelligence Nano Dagree.

---

## **Implementation Details**
### **Step 1: Generating Real Estate Listings**
I created **10+ synthetic real estate listings** using structured property data. Each listing contains:
- **Neighborhood**: Example: *Green Valley, Oakwood Estates*
- **Price**: Example: *$780,000*
- **Bedrooms**: Example: *4*
- **Bathrooms**: Example: *3*
- **House Size**: Example: *2,500 sqft*
- **Description**: Example: 
  *"A spacious, charming family home with an updated kitchen and a large backyard, perfect for gatherings."*
- **Neighborhood Description**: Example: 
  *"Green Valley is known for its excellent schools, parks, and strong community vibe."*

These listings were stored in **ChromaDB** as embeddings.

---

### **Step 2: Capturing Buyer Preferences**
To personalize listings, I collected buyer preferences such as:
- **Preferred home size**: *"Three-bedroom house with a spacious kitchen."*
- **Important factors**: *"Quiet neighborhood, good schools, and nearby shopping."*
- **Desired amenities**: *"A backyard, garage, and modern heating system."*
- **Transportation needs**: *"Close to public transport and highways."*

---

### **Step 3: Matching Listings Using Vector Search**
I converted both **listings and buyer preferences into embeddings** using **PyTorch**.  
Using **ChromaDB**, I performed **semantic searches** to retrieve listings that closely matched user needs.

---

### **Step 4: Personalized Listing Presentation**
For the top-matching listings, I presented:
- **Price, size, and details**
- **Neighborhood insights**
- **Images** (Displayed using `IPython.display`)