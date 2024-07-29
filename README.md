 - deno version

    ```
    deno 1.45.3 (release, aarch64-unknown-linux-gnu)
    v8 12.7.224.13
    typescript 5.5.2
    ```
 - ubuntu version

    ```
    Ubuntu 24.04 LTS
    ```

## Error: 

```bash
error: Uncaught (in promise) BadResource: Bad resource ID
    const result = await reader.read(inspectArr);
                                ^
    at read (ext:deno_io/12_io.js:117:28)
    at FsFile.read (ext:deno_fs/30_fs.js:711:12)
    at readDelim (https://deno.land/std@0.93.0/io/bufio.ts:652:33)
    at readDelim.next (<anonymous>)
    at readStringDelim (https://deno.land/std@0.93.0/io/bufio.ts:702:20)
    at readStringDelim.next (<anonymous>)
    at readLines (https://deno.land/std@0.93.0/io/bufio.ts:711:18)
    at readLines.next (<anonymous>)
    at waitForWSEndpoint (https://deno.land/x/puppeteer@16.2.0/src/deno/BrowserRunner.ts:168:20)
    at eventLoopTick (ext:core/01_core.js:168:7)
```

 - To replicate the error, run the following command

    ```bash
    PUPPETEER_PRODUCT=chrome deno run -A --unstable https://deno.land/x/puppeteer@16.2.0/install.ts
    ```
    ```bash
    deno run -A --unstable test-1.ts
    ```

 - test 2 is the code taken from [this](https://github.com/denoland/fresh/blob/3f78058ae91ad7215b6fa0d15ce8d0be88a47f1e/www/utils/screenshot.ts) deno repository

    ```bash
    deno run -A --unstable test-2.ts "https://media.istockphoto.com/id/1960673527/photo/fashion-designers.jpg?s=1024x1024&w=is&k=20&c=n1wnhIy5u2-6XSpKkcGrz3j9_NYRzniGWQMYxYWb3Fk=" 1
    ```