# Puppeteer

Puppeteer is a headless chrome runnning in node JS. 

It can be used to automate various actions and doing end to end tests directly from a backend for exemple. 

It can be used to generate pdf like this: 

```text
npm install puppeeter
```

In your code \(exemple for a nestjs project\): 

```text
import puppeteer from "puppeteer";

// In your controller.ts
async getPDF(@Param("results") results: string, @Res() response) {
        const buffer = await this.pdfService.getPdf(results);
        return response.send(buffer);
}

// In your pdfService.ts
async getPdf(results: string): Promise<any> {

       

        const targetUrl = `http://example.com`;
        const browser: puppeteer.Browser = await puppeteer.launch({
            headless: true,
            defaultViewport: null,
            args: ["--window-size=800,1200"],
        });
        const page: puppeteer.Page = await browser.newPage();
        await page.goto(targetUrl, { waitUntil: "load" });
        await page.emulateMediaType("print");

        const pdf = await page.pdf({
            format: "A4",
            margin: {
                left: "0px",
                top: "0px",
                right: "0px",
                bottom: "0px",
            },
        });

        await browser.close();
        return pdf;
}

```

You can call your pdf endpoint to get a pdf file of the url you set.

You probably will have to deal with some CSS rules if you want to print a beautiful CSS

{% page-ref page="../css/css-print.md" %}

[https://blog.risingstack.com/pdf-from-html-node-js-puppeteer/](https://blog.risingstack.com/pdf-from-html-node-js-puppeteer/)

