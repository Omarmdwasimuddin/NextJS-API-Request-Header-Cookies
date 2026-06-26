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

### Cookies
#### Click: cookies
![](https://imgur.com/xFC0Esv.png)
#### Add: Domain
![](https://imgur.com/DV1OeGs.png)
#### Add: cookie & Set: Value
![](https://imgur.com/XZyh0kY.png)
---

![](https://imgur.com/K6BpLxl.png)
```bash
import { cookies } from "next/headers";
import { NextResponse } from "next/server";


export async function GET(request:Request) {

    const cookieStore =await cookies();
    const tokenValue = cookieStore.get('token')
    
    return NextResponse.json(
        {status: "Success response", message: tokenValue},
        {status: 200}
    )
}
```
---

### response particular part: value or name or path
![](https://imgur.com/Eivl9Ov.png)
```bash
import { cookies } from "next/headers";
import { NextResponse } from "next/server";


export async function GET(request:Request) {

    const cookieStore =await cookies();
    const tokenValue = cookieStore.get('token')?.value
    
    return NextResponse.json(
        {status: "Success response", message: tokenValue},
        {status: 200}
    )
}
```
---
