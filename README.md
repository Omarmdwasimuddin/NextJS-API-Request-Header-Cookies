## NextJS API---> Header, Cookies

### Header
![](https://imgur.com/FUT3IzX.png)

```bash
import { headers } from "next/headers";
import { NextRequest, NextResponse } from "next/server";


export async function GET(request:NextRequest) {

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
import { NextResponse, NextRequest } from "next/server";


export async function GET(request:NextRequest) {

    const token = request.cookies.get('token');
    
    return NextResponse.json(
        {status: "success", message: token},
        {status: 200}
    )
}
```
---

### response particular part: value or name
![](https://imgur.com/Eivl9Ov.png)
```bash
import { NextResponse, NextRequest } from "next/server";


export async function GET(request:NextRequest) {

    const token = request.cookies.get('token')?.value
    
    return NextResponse.json(
        {status: "success", message: token},
        {status: 200}
    )
}
```
---
