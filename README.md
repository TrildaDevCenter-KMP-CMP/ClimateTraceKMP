![kotlin-version](https://img.shields.io/badge/kotlin-2.2.0-blue?logo=kotlin)

Kotlin/Compose Multiplatform project to show climate related emission data from https://climatetrace.org/data. Development just started so very much work in progress right now!
Have started with showing sector emission data per country but ton of other info available as well (ideas very welcome!).

Running on
* iOS (SwiftUI + shared Compose Multiplatform UI)
* Android
* Desktop
* Web (Wasm)
* Web (Kotlin/JS) - contributed by https://github.com/yogeshVU
* Kotlin Notebook
* MCP Server

The iOS client as mentioned includes shared Compose Multiplatform UI code.  It also includes option to use either SwiftUI or Compose code for the Country List screen (in both cases selecting a country will navigate to shared Compose emissions details screen).


<img width="669" alt="Screenshot 2024-04-29 at 21 13 54" src="https://github.com/joreilly/ClimateTraceKMP/assets/6302/d5d2a147-20f4-430b-9a14-17bc5526957e">



Related posts:
* [Kotlin MCP 💜 Kotlin Multiplatform](https://johnoreilly.dev/posts/kotlin-mcp-kmp/)
* [Initial exploration of using Koog for developing Kotlin based AI agents](https://johnoreilly.dev/posts/kotlin-koog/)
* [Using Google's Agent Development Kit for Java from Kotlin code](https://johnoreilly.dev/posts/kotlin-adk/)
  

### Android (Compose)

<img width="405" height="900" alt="Screenshot_20250824_175635" src="https://github.com/user-attachments/assets/bcce6d6e-85b2-4c27-aa12-eed898173b30" />




### iOS (SwiftUI/Compose)

![Simulator Screenshot - iPhone 15 Pro - 2023-12-10 at 19 31 59](https://github.com/joreilly/ClimateTraceKMP/assets/6302/ed0f6b1c-ce30-4f99-98d5-9bbdae49bcd3)




### Compose for Desktop 

<img width="1275" height="866" alt="Screenshot 2025-08-24 at 17 54 45" src="https://github.com/user-attachments/assets/534206cd-1a49-40ca-9a5f-3d7b54f4e4e5" />



### Compose for Web (Wasm)

<img width="1336" height="930" alt="Screenshot 2025-08-24 at 17 53 09" src="https://github.com/user-attachments/assets/9905a7bb-b10f-43a5-8428-7971a8ac4a9f" />



### Kotlin Notebook

<img width="694" alt="Screenshot 2023-12-14 at 20 33 45" src="https://github.com/joreilly/ClimateTraceKMP/assets/6302/82ed364a-0284-4e5c-b81e-40fdfc58f312">

**MCP Server**

The `mcp-server` module uses the [Kotlin MCP SDK](https://github.com/modelcontextprotocol/kotlin-sdk) to expose an MCP tools endpoint (returning per country emission data) that
can for example be plugged in to Claude Desktop as shown below.  That module uses same KMP shared code.

<img width="1608" alt="Screenshot 2025-07-06 at 17 24 20" src="https://github.com/user-attachments/assets/7e4fd599-3ade-47b7-bbe3-a4f36148c170" />


To integrate the MCP server with Claude Desktop for example you need to firstly run gradle `shadowJar` task and then select "Edit Config" under Developer Settings and add something 
like the following (update with your path)

```
{
  "mcpServers": {
    "kotlin-peopleinspace": {
      "command": "java",
      "args": [
        "-jar",
        "/Users/john.oreilly/github/ClimateTraceKMP/mcp-server/build/libs/serverAll.jar",
        "--stdio"
      ]
    }
  }
}
```


## Full set of Kotlin Multiplatform/Compose/SwiftUI samples

*  PeopleInSpace (https://github.com/joreilly/PeopleInSpace)
*  GalwayBus (https://github.com/joreilly/GalwayBus)
*  Confetti (https://github.com/joreilly/Confetti)
*  BikeShare (https://github.com/joreilly/BikeShare)
*  FantasyPremierLeague (https://github.com/joreilly/FantasyPremierLeague)
*  ClimateTrace (https://github.com/joreilly/ClimateTraceKMP)
*  GeminiKMP (https://github.com/joreilly/GeminiKMP)
*  MortyComposeKMM (https://github.com/joreilly/MortyComposeKMM)
*  StarWars (https://github.com/joreilly/StarWars)
*  WordMasterKMP (https://github.com/joreilly/WordMasterKMP)
*  Chip-8 (https://github.com/joreilly/chip-8)
