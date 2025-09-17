# Challenge 3: gRPC Service Testing with Bruno

## What is gRPC?

**gRPC (Google Remote Procedure Call)** is a high-performance, open-source RPC framework developed by Google. Key characteristics include:

- **Protocol Buffers (protobuf)**: Uses binary serialization format for efficient data transfer
- **HTTP/2**: Built on HTTP/2 for multiplexing and streaming
- **Language Agnostic**: Works across multiple programming languages
- **Type Safety**: Strongly typed service definitions

## Prerequisites
- Bruno with gRPC support enabled

## Step-by-Step Instructions

### Step 1: Enable gRPC Support
1. Open Bruno and create collection with name **echo-grpc** from context menu
2. Navigate to **Settings** > **Beta**
3. Enable **gRPC Support** 

### Step 2: Create a gRPC Request
1. Create a new **gRPC** request
2. Configure the request:
   - **Name**: `echo-grpc`
   - **URL**: `grpcs://grpcb.in`

### Step 3: Select gRPC Method
1. Click on the **method** (dropdown)
2. From the available methods, select **`SUM`**
   - This method performs addition of two numbers

### Step 4: Configure the Message
1. Navigate to the **Message** section
2. Click the **auto fill icon** (🔄) to generate a sample message
3. The auto-generated message should contain two numeric values to be added

### Step 5: Execute the Request
1. Click the **Send** button to execute the gRPC call
2. Wait for the response to be processed

### Step 6: Verify the Response
Your response should contain the addition result in the following format:

```json
{
  "v": "addition-of-num",
  "err": ""
}
```

**Response Explanation:**
- `v`: Contains the result of the addition operation
- `err`: Error field (empty string indicates success)

## Expected Results
- **Response Format**: JSON-like structure with `v` and `err` fields
- **Calculation**: The `v` field should contain the sum of the two numbers sent in the message
- **Error Handling**: The `err` field should be empty, indicating successful execution


