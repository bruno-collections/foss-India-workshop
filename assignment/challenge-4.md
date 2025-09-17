# Challenge 4: API Scripting with Bruno

## What is API Testing Scripting?

**API Testing Scripting** allows you to write custom JavaScript code to enhance your API tests with:

- **Pre-request Scripts**: Code that runs before sending the request (authentication, data preparation)
- **Post-response Scripts**: Code that runs after receiving the response (validation, data extraction)
- **Test Scripts**: Code that validates responses and performs assertions


## Step-by-Step Instructions

### Step 1: Create an HTTP Request
1. Open Bruno and create collection with name **echo-script** from context menu
2. Create a new **HTTP** request
3. Configure the request:
   - **Name**: `echo-bruno`
   - **URL**: `https://echo.usebruno.com`
   - **Method**: `POST` 

### Step 2: Write a Pre-request Script
1. Navigate to the **Script** tab
2. In the **Pre-request Script** section, add the following conditional statement:

```javascript
// Check if the request URL contains 'echo'
if (req.url.includes('echo')) {
    console.log('keyword found');
} else {
    console.log('not found');
}
```

**Script Explanation:**
- `req.url`: Bruno's built-in variable containing the request URL
- `includes('echo')`: JavaScript method to check if string contains substring
- `console.log()`: Outputs messages to the console for debugging

### Step 3: Open Dev Tools
1. Open **Developer Tools** button (bottom-right corner)
2. Go to console panel
3. Keep it visible to see the script output

### Step 4: Execute the Request
1. Click the **Send** button to execute the request
2. Watch the console for the script output

### Step 5: Verify the Console Output
You should see the message **"keyword found"** in the console because:
- The URL `https://echo.usebruno.com` contains the word "echo"
- The conditional statement evaluates to `true`
- The script executes `console.log('keyword found')`

## Expected Results
- **Console Output**: "keyword found" message should appear
- **Response**: The echo service should return the request details
- **Script Execution**: The pre-request script should run before the HTTP call