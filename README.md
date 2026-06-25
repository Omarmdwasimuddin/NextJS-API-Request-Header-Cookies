## NextJS API---> Header, Cookies

### Header
![](https://imgur.com/FUT3IzX.png)

```bash
import { headers } from "next/headers";
import { NextResponse } from "next/server";


export async function GET(request:Request) {

    const headerList = headers();
    const apiKey = (await headerList).get('api-key');
    
    return NextResponse.json(
        {status: "Success response", message: apiKey},
        {status: 200}
    )
}
```
---
