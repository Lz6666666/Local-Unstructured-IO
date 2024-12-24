Langflow Setup and Usage Guide
This README provides a step-by-step guide to setting up and using Langflow with the
Unstructured IO API. Follow the instructions below to successfully configure your
environment and use the application to process PDF, DOCX, or TXT files.
---------------------------------------------------------------------------
Prerequisites
Ensure the following are installed and configured on your system:
- Docker
- Langflow
- A stable internet connection
---------------------------------------------------------------------------
Step 1: Set Up Unstructured IO in Docker
1. Open power shell terminal and run the following command to set up the
Unstructured IO API in Docker:
 docker run -p 8000:8000 -d --rm --name unstructured-api
downloads.unstructured.io/unstructured-io/unstructured-api:latest
2. Verify that the container is running by executing:
 docker ps

You should see a container named `unstructured-api` in the list.
---------------------------------------------------------------------------
Step 2: Identify the IP Address of the Host
To interact with the Unstructured IO API, you need to identify the IP address of the
Docker container host:
On Windows:
 1. Open Settings.
 2. Navigate to Network & Internet.
 3. Select your active network (e.g., Wi-Fi or Ethernet).
 4. Scroll down to the Properties section and locate the IPv4 Address.
OR
Using Command:
 - On Windows:

 ipconfig

 Look for the IPv4 Address under the network adapter you're using.
 - On Linux/Mac:
 ifconfig

 Look for the `inet` field corresponding to your active network interface.
- Note this IP address. Replace `localhost` in the API URL with this IP address.
---------------------------------------------------------------------------
Step 3: Start Langflow
1. Open a terminal and start Langflow by running:

 langflow

2. Access Langflow in your web browser by navigating to:

 http://localhost:7860

---------------------------------------------------------------------------
Step 4: Configure Custom Component
1. In Langflow, locate your **Custom Component** module.
2. Enter the Unstructured IO API URL in the following format:

 http://<IP_ADDRESS>:8000/general/v0/general
 For example, if your IP address is `192.167.1.88`, the URL should be:
 http://192.167.1.88:8000/general/v0/general

---------------------------------------------------------------------------
Step 5: Upload Files
1. In the Custom Component module, upload a file in one of the supported formats:
 - PDF
 - DOCX
 - TXT
2. The system will process the file and provide the required output.
3. Run the program by clicking the small triangle in the upper right corner of the chat
output component, and the answer will be printed in the playground in the lower right
corner of the screen.
---------------------------------------------------------------------------
Troubleshooting
Cannot connect to Unstructured IO API
- Ensure the Docker container is running by checking with `docker ps`.
- Verify that the correct IP address is used in the API URL.
Cannot access Langflow
- Ensure Langflow is running and accessible at `http://localhost:7860`.
- Verify there are no firewall or network restrictions.
---------------------------------------------------------------------------
Feel free to reach out if you encounter any issues or need further assistance!
