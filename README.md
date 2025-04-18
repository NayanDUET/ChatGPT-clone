 # Make a ChatGPT clone

You don't know any technology and you want to clone ChatGPT it's just for you. Just follow the step by step process.You need a code editor like VS code.Make a folder and open it with VS code.

Now we need a user interface(UI).For this we use assistant-ui template. Copy and run on VS code terminal.By the way you have to install node js in your computer.Go to node js website download and install it.This project built in react js and next js.

```sh
npx assistant-ui@latest create
```

Its take some time. When it's complete, your UI is ready for showing.For this run VS code terminal and copy and paste it.
```sh
npm run dev
```
Then it's show a url like http://locashost:3000. Click and Go there for check.I hope everything alright.Our fontend is ready.Now work with backend.For this we use a API.Google gemini API help us as its free (ChatGPT API is paid).Now just Copy and paste it on VS code terminal.

```sh
npm install ai @assistant-ui/react-ai-sdk @ai-sdk/google
```
Now we need some changes.Go to this directory
```sh
/app/api/chat/route.ts
```
And paste it.
```sh
import { google } from "@ai-sdk/google";
import { streamText } from "ai";
 
export const maxDuration = 30;
 
export async function POST(req: Request) {
  const { messages } = await req.json();
  const result = streamText({
    model: google("gemini-2.0-flash"),
    messages,
  });
  return result.toDataStreamResponse();
}
```
In you main project directory create a file name ".env.local" then open the file and paste it.
```sh
GOOGLE_GENERATIVE_AI_API_KEY="xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```
Now it's time to place our orginal API key.For this go to 'google ai studio' Take a API key and replace.We are almost done !!!
It's time to play......... go to VS code terminal and paste it.
```sh
npm run dev
```
Then it's show a url like http://locashost:3000.YES!! you done your own version of ChatGPT.IF you want to share the project then you have to deploy this project.






