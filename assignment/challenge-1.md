# REST API

1. Create req in Bruno with method `POST`, name `echo` and URL `https://echo.usebruno.com`

2. Go to body tab and select `JSON` as body type and add following:
```json
{
    "name":"your-name",
    "event": "FOSS India",
    "love-opensource": true
}
```

3. Go to assert tab and click `Add Assertion`  button and enter following data:

<table>
<tr>
    <th> Expr </th>
    <th> Operator </th>
    <th> Value </th>
</tr>
<tr>
    <td> res.status</td>
    <td> equals</td>
    <td> 200 </td>
</tr>
</table>

4. Go to test tab, write folowing script:
```js

test("verify res have name property", function() {
    expect(res.body.name).to.eql("your-name")
})
```

5. Execute the req

After following above steps, you will recieve `your-name` in `Response` tab and `verify res have name property` turn into green in `Test` tab.

