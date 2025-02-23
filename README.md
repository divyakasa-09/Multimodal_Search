# Multimodal_Search


## **Project Overview**
The food delivery industry is highly competitive, and **personalized recommendations** play a crucial role in improving **user engagement and customer satisfaction**. Existing recommendation systems primarily rely on **text-based** data, missing out on **visual appeal**—a critical factor in food choices.

This project introduces a **Multimodal Retrieval-Augmented Generation (RAG) System** that combines **textual and visual data** to enhance food recommendations for a restaurant aggregator platform. By leveraging **AI-powered models**, the system delivers **context-aware, personalized suggestions** based on users' preferences and uploaded food images.

---
## DEMO


🔗 **[Click here to watch the demo](https://drive.google.com/file/d/1MD0P1xVqvf351PQe29GJIH87EqYzSbl_/view?usp=sharing)**  

---
### **Why This Matters?**
✅ **Better User Experience:** Helps users find food that matches their taste, dietary preferences, and visual appeal.  
✅ **Improved Customer Retention:** More relevant suggestions increase app engagement and return users.  
✅ **Higher Revenue for Restaurants:** Personalized recommendations can lead to increased order values and frequency.  
✅ **Advanced AI Capabilities:** Uses **Generative AI** and **Vector Search** to improve accuracy.  

---

## **How It Works?**
1. **User Input:**  
   - Users **search for a dish** (e.g., “Spicy Mexican Tacos”)  
   - OR **upload an image** of a meal they liked.  

2. **Multimodal AI Processing:**  
   - Text queries are processed with **AWS Titan Embeddings** (Vector Search).  
   - Images are analyzed using **Claude-Sonnet Multimodal AI** to generate descriptions.  

3. **Food Matching Engine (FAISS + AWS Bedrock):**  
   - Finds **visually & textually similar** dishes using FAISS (Facebook AI Similarity Search).  
   - Identifies **matching cuisines, ingredients, dietary details**.  

4. **Chatbot Response (Streamlit UI):**  
   - Users receive **personalized recommendations** through an interactive chatbot.  
   - Includes **dish name, ingredients, nutrition, restaurant details, price, and ratings**.  

---

## **Technology Stack**
- **AI & NLP Models:** Claude-Sonnet Multimodal, AWS Titan Embeddings  
- **Vector Search:** FAISS (Facebook AI Similarity Search)  
- **Cloud Services:** AWS Bedrock, S3, AWS Lambda  
- **Backend:** Python (LangChain, Pandas, boto3)  
- **Frontend:** Streamlit (Interactive UI)  

---

## **Setup & Installation**
### **Step 1: Clone the Repository**
```bash
git clone https://github.com/your-repo/multimodal-rag.git
cd multimodal-rag
```

### **Step 2: Set Up Virtual Environment**
#### **For Windows**
```bash
python -m venv venv
venv\Scripts\activate
```
#### **For Linux/macOS**
```bash
python3 -m venv venv
source venv/bin/activate
```

### **Step 3: Install Dependencies**
```bash
pip install -r requirements.txt
```

### **Step 4: AWS Configuration**
Ensure you have AWS credentials set up:
```bash
aws configure
```
- Enter **AWS Access Key** & **Secret Key**
- Set default **region** (e.g., `us-east-1`)

### **Step 5: Request Access to Amazon Bedrock**
1. Log in to **AWS Console** → Search for **"Bedrock"**.
2. Click **Manage Model Access**.
3. Enable **Claude-Sonnet Multimodal** & **Amazon Titan Embeddings**.

---

## **Running the Application**
### **Step 1: Start the Streamlit App**
```bash
streamlit run app.py
```
- The chatbot interface will open.
- Users can **search by text** or **upload food images** for recommendations.

### **Step 2: Image-Based Recommendations**
- If a user uploads a **food image**, it is processed by **Claude-Sonnet Multimodal AI**.
- The system **matches the dish visually** and provides similar food options.

---

## **System Architecture**
### **Data Flow**
1. **User Query (Text/Image) →** Processed by AI models.  
2. **Embedding & Vectorization →** Stores data in FAISS.  
3. **Search & Retrieval →** Matches with stored food database.  
4. **Response Generation →** Chatbot provides recommendations.  

### **Components**
- **`app.py`** → Main Streamlit UI (Handles chat & AI interactions).  
- **`utils.py`** → Helper functions (Image processing, AI queries, FAISS search).  
- **`multimodal-llm.ipynb`** → Jupyter Notebook for data preprocessing & model testing.  

---

## **Deployment on AWS EC2 (Optional)**
### **Step 1: Launch EC2 Instance**
- Select **Ubuntu 22.04**.
- Allow inbound traffic on **port 8501**.

### **Step 2: Transfer Files**
```bash
scp -i your-key.pem -r * ubuntu@your-ec2-instance-ip:/home/ubuntu/
```

### **Step 3: Install Dependencies**
```bash
sudo apt update && sudo apt install python3-pip
pip3 install -r requirements.txt
```

### **Step 4: Run the Application**
```bash
nohup streamlit run app.py --server.port 8501 &
```
- Access the app at `http://your-ec2-instance-ip:8501`.

---

## **Example Usage**
### **Text Query**
💬 **User Input:** *"Recommend me a high-protein vegetarian meal."*  
🟢 **Response:**  
```
Here are some high-protein vegetarian options:
1. **Grilled Tofu Salad** - Rich in protein, fresh greens, and sesame dressing.
2. **Chickpea Curry** - A protein-packed Indian dish with turmeric and spices.
```

### **Image Query**
📷 **User Uploads:** A food image.  
🔍 **AI Generates Description:**  
*"This looks like a cheese-stuffed pizza with tomato and basil topping."*  
✅ **Recommended Similar Dishes:**  
1. **Margherita Pizza (Italy)**  
2. **Cheesy Garlic Bread**  

---

## **Key Business Impact**
### **For Restaurant Aggregators**
📈 **Higher Customer Engagement:** Personalized recommendations improve user experience.  
🍽 **Better Order Conversions:** Visually appealing suggestions encourage food discovery.  
💰 **Increased Revenue:** Targeted food recommendations boost repeat orders.  

### **For Users**
✅ **Find Food Easily:** More **accurate & visually relevant** dish suggestions.  
✅ **Personalized Results:** Considers **dietary preferences, calories, cuisine type**.  
✅ **Seamless Experience:** Chatbot interaction feels **natural & engaging**.  

---

## **Troubleshooting**
### **Issue 1: AWS Bedrock Model Not Found**
- Ensure **Claude-Sonnet Multimodal** & **AWS Titan Embeddings** are **enabled**.

### **Issue 2: FAISS Index Not Found**
- Run `multimodal-llm.ipynb` to regenerate FAISS index.

### **Issue 3: Streamlit App Not Running**
- Ensure dependencies are installed:
```bash
pip install -r requirements.txt
```

---

## **Future Enhancements**
🚀 **Support for More Cuisines** – Expand dataset for diverse food preferences.  
🚀 **Voice-Based Queries** – Enable **speech-to-text** for food recommendations.  
🚀 **Real-Time Data Updates** – Fetch **live restaurant menus** for up-to-date results.  

---

## **Conclusion**
This project showcases **AI-powered personalized food recommendations** by integrating **text & image data**. Using **AWS Bedrock, FAISS, and Streamlit**, it delivers a **business-ready solution** for restaurant aggregators.  

Want to contribute? **Fork the repo, suggest improvements, and help refine AI-driven food discovery!** 🚀