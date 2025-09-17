# Challenge 5: Environment Management in Bruno

## What are API Testing Environments?

**Environment Management** in API testing allows you to:

- **Separate Configurations**: Use different settings for development, testing, and production
- **Variable Substitution**: Use placeholders that get replaced with environment-specific values
- **Easy Switching**: Quickly change between different environments without modifying requests

## Step-by-Step Instructions

### Step 1: Access Environment Settings
1. Open Bruno from context menu with name **echo-environment** 
2. Look for the environment selector in the top-right corner (shows "No Environment")
3. Click on the environment dropdown

### Step 2: Create Local Environment
1. Click **Configure**
2. Set the environment name to **Local**
3. Add the following variables:

| Variable Name | Variable Value |
|---------------|----------------|
| `url` | `https://echo.usebruno.com` |
| `name` | `Local` |

### Step 3: Create Test Environment
1. Create another environment named **"Test"**
2. Add the same variables with Test-specific values:

| Variable Name | Variable Value |
|---------------|----------------|
| `url` | `https://echo.usebruno.com` |
| `name` | `Test` |

### Step 4: Create Production Environment
1. Create a third environment named **"Prod"**
2. Add the same variables with Production-specific values:

| Variable Name | Variable Value |
|---------------|----------------|
| `url` | `https://echo.usebruno.com` |
| `name` | `Prod` |

### Step 5: Create Environment-Aware Request
1. Create a new **HTTP** request
2. Configure the request:
   - **Name**: `echo-env`
   - **URL**: `{{url}}` (using environment variable)
   - **Method**: `POST`

### Step 6: Configure Request Body
1. Navigate to the **Body** tab
2. Select **JSON** as the body type
3. Add the following JSON payload:

```json
{
    "name": "{{name}}"
}
```

**Variable Usage:**
- `{{url}}`: Will be replaced with the environment's URL value
- `{{name}}`: Will be replaced with the environment's name value

### Step 7: Test Environment Switching

#### Test Local Environment
1. Select **"Local"** from the environment dropdown
2. Send the request
3. **Expected Response**: The response should contain `"name": "Local"`

#### Test Test Environment
1. Select **"Test"** from the environment dropdown
2. Send the same request
3. **Expected Response**: The response should contain `"name": "Test"`

#### Test Production Environment
1. Select **"Prod"** from the environment dropdown
2. Send the same request
3. **Expected Response**: The response should contain `"name": "Prod"`

## Expected Results

### Local Environment Response
```json
{
    "name": "Local",
    "url": "https://echo.usebruno.com",
    "method": "POST"
}
```

### Test Environment Response
```json
{
    "name": "Test",
    "url": "https://echo.usebruno.com",
    "method": "POST"
}
```

### Production Environment Response
```json
{
    "name": "Prod",
    "url": "https://echo.usebruno.com",
    "method": "POST"
}
```

