**Agentic Insurance Claim Processor**

A smart, end-to-end insurance claim processing app using LangGraph, Snowflake Cortex Document AI, Claude Vision, and Mistral — all wrapped in a clean Streamlit UI.



**Project Summary**

I had the opportunity to build an end-to-end insurance claim processor using agentic AI principles. The system guides uploaded documents—a driver’s license, a claim form, and a car damage photo—through a structured workflow powered by LangGraph. Each step acts as an intelligent agent: Snowflake Cortex extracts data from documents, Claude analyzes the car image and performs multi-source comparisons, and Snowflake verifies policy validity. Finally, Mistral generates a professional email response based on the claim outcome. The goal was to simulate how a thoughtful human agent would handle claims—accurately, step-by-step—with transparency and automation.


**Features**

Extracts info from driver's license, claim form, and car photo
LangGraph manages each step like an agent (upload → extract → analyze → compare)
**Snowflake Document AI** for structured field extraction
Claude (via Amazon Bedrock) performs intelligent visual + text-based comparisons
Verifies policy validity by querying Snowflake with customer ID
Mistral writes an email explaining the final claim decision




**Getting Started**

Clone the Repository
git clone https://github.com/curious-bigcat/insurance_agentic_ai.git
cd insurance_agentic_ai


**Create Virtual Environment**


python3 -m venv venv
source venv/bin/activate


**Install Dependencies**

pip install -r requirements.txt


**Set Environment Variables**

Create a `.env` file in the root directory:
{
  SNOWFLAKE_ACCOUNT=your_account
SNOWFLAKE_USER=your_user
SNOWFLAKE_PASSWORD=your_password
SNOWFLAKE_ROLE=your_role
SNOWFLAKE_WAREHOUSE=your_wh
SNOWFLAKE_DATABASE=your_db
SNOWFLAKE_SCHEMA=your_schema
}



**Run the App**




**Workflow Steps**

- Uploaded  
- DL Extracted  
- Claim Extracted  
- Car Analyzed  
- Merged & Compared  

**Comparison Result**

```json
{
  "full_name": { "match": true, "dl_value": "Steven Smith", "claim_value": "Steven Smith" },
  "dl_number": { "match": true, "dl_value": "DL-2605979475", "claim_value": "DL-2605979475" },
  "vehicle_color": { "match": true, "image_value": "Dark Purple", "claim_value": "Dark Purple" },
  "vin": { "match": true, "extracted_from_claim": "KA81JS7515", "customer_record_value": "KA81JS7515" }
}
```

**Email Generated (Mistral)**

> Dear Valued Customer,  
> We have reviewed your insurance claim filed on **Feb 14, 2025** under a valid policy ending **June 18, 2025**.  
> Based on our review of your documents and car image, your claim has been **accepted**.  
> Thank you for choosing us.

---


**Author & Maintainer**

Built with ❤ [@curious-bigcat](https://github.com/curious-bigcat)
