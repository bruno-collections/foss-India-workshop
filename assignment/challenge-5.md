# Create Environment 

1. Open Bruno 
2. Go to top right corner and click on `No Environment`
3. Create collection environment with title:

- Local 
- Test
- Prod

with two values each:
<table>
<tr>
<th> Name </th>
<th> Value </th>
</tr>
<tr>
<td> url</td>
<td> https://echo.usebruno.com</td>
</tr>
<tr>
<td> name</td>
<td> Local</td>
</tr>
</table>

Create three separate environments (Local, Test, Prod) with the same table structure, replacing "Local" with "Test" and "Prod" respectively in the Name field for each environment. 

4. Create a single `HTTP` req with name `echo-env` and URL `{{url}}`

5. Go to body and select JSON from dropdown and add
```json
{
    "name": {{name}}
}
```

6. Test the environment switching:
   - Switch to **Local** environment and send the request - you should see `"name": "Local"` in the response
   - Switch to **Test** environment and send the request - you should see `"name": "Test"` in the response  
   - Switch to **Prod** environment and send the request - you should see `"name": "Prod"` in the response

**Expected Result:** The response body should dynamically change based on the selected environment, demonstrating how environment variables work in Bruno.

