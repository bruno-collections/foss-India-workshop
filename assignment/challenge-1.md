# Challenge 1: REST API Testing with Bruno

## What is REST API?

**REST (Representational State Transfer)** is an architectural style for designing web services. REST APIs use standard HTTP methods to perform operations on resources:

- **GET**: Retrieve data from a server
- **POST**: Send data to a server to create a new resource
- **PUT**: Update an existing resource
- **DELETE**: Remove a resource
- **PATCH**: Partially update a resource

REST APIs typically return data in JSON format and use HTTP status codes to indicate success or failure.

## Step-by-Step Instructions

### Step 1: Create a POST Request
1. Open Bruno
2. Create a collection from context menu with name **echo-bruno** 
3. Create new request with the following details:
   - **Method**: `POST`
   - **Name**: `echo`
   - **URL**: `https://echo.usebruno.com`

### Step 2: Configure Request Body
1. Navigate to the **Body** tab
2. Select **JSON** as the body type
3. Add the following JSON payload:
```json
{
    "name": "your-name",
    "event": "FOSS India",
    "love-opensource": true
}
```

### Step 3: Add Response Assertions
1. Go to the **Assert** tab
2. Click the **Add Assertion** button
3. Configure the assertion with the following values:

| Field | Value |
|-------|-------|
| **Expression** | `res.status` |
| **Operator** | `equals` |
| **Expected Value** | `200` |

### Step 4: Write Test Script
1. Navigate to the **Test** tab
2. Add the following test script:
```javascript
test("verify res have name property", function() {
    expect(res.body.name).to.eql("your-name")
})
```

### Step 5: Execute and Verify
1. Click the **Send** button to execute the request
2. Check the **Response** tab - you should see your JSON data echoed back
3. Check the **Test** tab - the test "verify res have name property" should show as **PASSED** (green)

## Expected Results
- **Response Status**: 200 OK
- **Response Body**: Your JSON payload should be returned exactly as sent
- **Test Result**: "verify res have name property" should pass
- **Assertion**: Status code assertion should pass


