---
title: City Compass
emoji: 🧭
colorFrom: blue
colorTo: orange
sdk: streamlit
sdk_version: 1.55.0
app_file: app.py
pinned: false
license: apache-2.0
---

# 🧭 City Compass — City Museum Visitor Assistant

**City Compass** is an AI-powered chatbot designed to help visitors plan a trip to **City Museum in St. Louis, Missouri**. It answers common questions about admission, hours, parking, accessibility, attractions, and visitor policies in a conversational format.

This project was created for **ISA 414/514 — Assignment 4**. The app is built with **Python**, **Streamlit**, and the **OpenAI API**, following the structure of the RX Pizzeria example provided in class.

## What the chatbot does

- Answers frequently asked visitor questions about City Museum.
- Helps visitors prepare for a trip and identify useful information before arriving.
- Maintains conversation history during the Streamlit session.
- Streams responses as they are generated using the `gpt-5-mini` model.
- Uses a custom grounding prompt stored securely in Streamlit Secrets to guide its behavior.

**Important:** Prices, hours, availability, and policies may change. The assistant should direct visitors to [City Museum's official website](https://citymuseum.org/) for current details and avoid claiming it can make bookings or access live inventory.

## Repository files

| File | Purpose |
| --- | --- |
| `app.py` | Main Streamlit chatbot application |
| `requirements.txt` | Required Python packages |
| `logo.png` | City Compass logo displayed by the app **(upload this file before deployment)** |
| `README.md` | Project overview and setup instructions |

## Run the app locally

1. Install Python and download or clone this repository.
2. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Create `.streamlit/secrets.toml` in your local project folder with your own API key and chatbot instructions:

   ```toml
   OPENAI_API_KEY = "YOUR_OPENAI_API_KEY"
   GROUNDING = """
   You are City Compass, a helpful virtual visitor assistant for City Museum in St. Louis, Missouri.
   Answer questions about planning a museum visit. Be clear and friendly.
   Do not invent current prices, hours, availability, policies, or accessibility details.
   If information could have changed, recommend checking https://citymuseum.org/.
   Do not claim you can sell tickets, make reservations, or access live museum systems.
   """
   ```

4. Ensure `logo.png` is in the same folder as `app.py`.
5. Start the app:

   ```bash
   streamlit run app.py
   ```

## Deploy with Streamlit Community Cloud

1. Upload `logo.png` to the root of this GitHub repository, alongside `app.py`.
2. Go to [Streamlit Community Cloud](https://share.streamlit.io/) and create a new app from GitHub.
3. Select repository `leinaujc-png/ISA-414-Assignment-4`, branch `main`, and main file `app.py`.
4. In **Advanced settings → Secrets**, add your real `OPENAI_API_KEY` and your complete `GROUNDING` prompt in the format shown above.
5. Deploy the app and test several questions to confirm its answers and behavior.

**Security:** Never commit an API key or a `.streamlit/secrets.toml` file containing real credentials to this public repository.

## Example questions

- What should I know before visiting City Museum?
- Where can I find current ticket prices?
- Does City Museum have parking?
- What should I check before visiting with children?
- Where can I find information about accessibility?

## Resources

- [City Museum — Official Website](https://citymuseum.org/)
- [Streamlit Documentation](https://docs.streamlit.io/)
- [OpenAI API Documentation](https://platform.openai.com/docs/)
- [RX Pizzeria class example](https://github.com/rayna-xu-is/RXpizzeria)

*This chatbot is an educational project and is not an official City Museum customer-service channel.*
