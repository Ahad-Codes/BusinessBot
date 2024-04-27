# OnlyBusiness

Motivation:

Problem:
Managing WhatsApp businesses is a time-consuming process. It primarily involves handling customer queries and requires manual intervention for handling orders, other human-facing tasks. Since these businesses are usually small, with limited resources, and operating with small teams, this can become burdensome for the team. Automation in this area can help with this significantly.

Relevance:
WhatsApp business communication is primarily text-based, offering a substantial opportunity for leveraging generative AI (genAI) models to automate various aspects of business management. This is particularly relevant for small businesses with limited resources, as automation can enable them to handle a larger workload with fewer personnel. Given the widespread adoption of WhatsApp for business communication and the ease of entry into this market, there exists a large potential user base for solutions that alleviate the manual burden of managing these businesses.

Impact:
By automating order processing, customer inquiries, and other routine tasks, businesses can operate more efficiently and focus their resources on growth and customer satisfaction. This automation has the potential to elevate WhatsApp businesses to a higher level of professionalism and scalability, enabling them to compete more effectively in the market with bigger businesses. Additionally, as there are currently limited tools supporting WhatsApp business automation, such a solution could fill a significant gap in the market and become a valuable asset for small businesses seeking to optimise their operations.

Goal:
The goal of the project is to empower small businesses by providing them with an efficient solution to manage their workload. These are the angles we want to address:
● Streamlining Order Management: One key objective is to streamline the process of order management for small businesses operating on WhatsApp. This includes automating tasks such as order processing, inventory management, and order tracking, thereby reducing manual effort and minimising errors.
● Boosting Sales: Another objective is to improve customer engagement and increase sales by automating a recommendation system to provide personalised recommendations based on past purchases with the business.
● Enabling Scalability: The project seeks to enable scalability for small businesses by providing them with tools and features that can handle redundant tasks. This includes scalability in terms of handling increasing order volumes, expanding product offerings, and catering to a growing customer base, without significant additional investment in infrastructure.

Target Audience:
The primary audience for the project includes small business owners and managers who operate on WhatsApp as a primary communication and sales channel.

Differentiating Factor:
Other products do exist for supporting WhatsApp businesses, however they are primarily leveraging chatbot APIs for answering user questions. Our product aims to help both the owner and the customer.
We will be providing several order-placement interfaces to choose from. The owners will be able to provide a document that our bot will use to answer customer’s queries. They will also periodically get generated reports using the recent sales and chat data. The customers will also be able to ask the Whatsapp bot for more complex requests, such as questions about their own order history and even product recommendations.

Approach:
We intend to use RAG to answer the majority of the customer’s queries, which will be according to the document provided by the business owners. This is because the majority of customer queries tend to be predictable, and out of domain questions are very unlikely. The usage of certain words can trigger the bot to make changes to the Google Sheet, which acts as the inventory. For speech inputs, we intend to use a transcription model to convert it into text, before following the same steps.
We will try both MMS and Whisper, and select the one with better performance. For the RAG and Function Calling, we will use the OpenAI assistant API. We will not be comparing against different models because OpenAI Assistant is only available for GPT 4 and above. The multilingual support will be handled by prompting the model to answer in the same language as the query. We will be limiting the speech languages to English.
We believe that for the user to be able to ask the bot to analyse their data on their behalf makes our model very practical. Below are a general description of how the model will work and the major use cases we are targeting.



Major Use Cases:

Voicenote Capability:
Upon receiving a voice note, our system will leverage a transcription model to convert the audio content into text format. Subsequently, this transcribed text will be forwarded to the Chatbot for processing by our OpenAI assistant. The assistant will then execute its typical procedures, utilising both its knowledge base and data accessed through the Google Sheets API to provide accurate responses to user inquiries. This integration seeks to enhance user engagement and streamline communication with the Chatbot by introducing a more versatile input method.

Manager Reports:
The bot will also act as a reporting system for the company's Manager, facilitating efficient daily updates on business operations. Leveraging the capabilities of the
OpenAI assistant, the system will autonomously retrieve data from Google Sheets and generate comprehensive analytical reports. The Manager will also have the ability to query the Chatbot for real-time business information, as it will be granted full access to the company's data repository. This initiative aims to provide the Manager with timely insights and empower informed decision-making through seamless access to business data.

Recommendation Systems:
The bot will be able to give personalised product recommendations to users based on their previous purchases. The bot will also be able to recommend products similar or related to the product that the user is currently ordering, during the order placement. The user themselves can also prompt the bot and ask it to recommend products based on their recent purchase history.
This would provide users with a more personalised experience, tailored to their needs.

User Reports:
Users can engage with the chatbot to inquire about details regarding their past purchases, retrieving vital information about their orders. They have the capability to delve into comprehensive data analysis, empowering them to make informed decisions. For instance, users can ask the total expenditure incurred across all transactions, or ask for a summary of all their past orders, thus gaining insights into their spending habits. Some example questions are: "Can you list all the orders I placed on [specific date]?", "What payment method did I use for my last three orders?" and "What was the rating I gave for my most recent purchase?".
The processing of these requests will be very similar to how manager reports are generated. The only difference should be the amount of data the customer has access to, i.e only their own past orders.
