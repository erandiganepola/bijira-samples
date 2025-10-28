# App Recommendations API Proxy from GitHub Repository

## Use case

This sample demonstrates how to create a proxy for an App Recommendations API using a GitHub repository. 
The API Proxy component will forward requests to the actual App Recommendations API, allowing you to manage and monitor the API traffic.

The App Recommendations API provides personalized app recommendations based on device specifications, user preferences, and contextual information. 
By creating a proxy for this API, you can add additional layers of security, rate limiting, and analytics.

The following steps will guide you through the process of creating and deploying the App Recommendations API Proxy component in Bijira:

1. **Create the API Proxy**: Create the API Proxy using the provided sample values.
2. **Configure and Deploy the API Proxy**: Configure the necessary settings and deploy the API proxy to make it available for use.
3. **Test the API Proxy**: Use the OpenAPI Console in Bijira to test the API Proxy and ensure it is functioning correctly.

## Run the sample in Bijira

### Prerequisites

- A valid Bijira account with available resource quota.

### Create the API Proxy

1. Go to [https://console.bijira.dev/](https://console.bijira.dev/) and sign in. This opens the project home page.
2. Choose **My APIs (Ingress)** option and select **Import API Contract**.
3. Select **URL** option and provide the following URL to import the API contract from the GitHub repository:
   ```
   https://raw.githubusercontent.com/wso2/bijira-samples/refs/heads/main/app-recommendations/openapi.yaml
   ```
4. Click **Next** and edit pre-defined values as needed. You can keep the default values for this sample.
5. Click **Create** to create the API Proxy. Wait for the setup to complete.

### Configure and Deploy the API Proxy

1. Navigate to the **Deploy** page of the API Proxy.
2. Click **Configure and Deploy** button.
3. Select **External** as API Access Mode.
4. Click **Deploy**.

## Test the API Proxy

1. Navigate to the **Test --> OpenAPI Console** page of the API Proxy.
2. Use the OpenAPI Console to test the API Proxy.

### API Proxy Behavior

***The App Recommendations API Proxy provides the following functionality:***

- **POST /getAppRecommendations**: Returns personalized app recommendations based on device specifications and user context. 

#### Request Parameters

The endpoint accepts the following parameters in the request body:

- `aaid` (required): Advertising ID (UUID format)
- `deviceSpec` (required): Device specification tier (e.g., "high-end")
- `deviceManufacturer` (required): Device manufacturer name (e.g., "Samsung")
- `deviceModel` (required): Device model name (e.g., "Galaxy S21")
- `osVersion` (required): Operating system version (integer)
- `deviceLanguage` (required): Device language setting (e.g., "en-US")
- `deviceGeo` (required): Device geographic location/country code (e.g., "US")
- `userExperience` (required): User experience preference
- `category` (required): Preferred app category (e.g., "Games")
- `remainingSpace` (required): Remaining storage space in MB (integer)
- `contextStrings` (optional): Array of contextual tags for better recommendations

#### Response

The API returns an array of recommendations, each containing:
- App details (title, icon, category)
- Recommendation rationale
- Deep links for installation
- Unique bid identifier
- App ranking information