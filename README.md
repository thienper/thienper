- 👋 Hi, I’m @thienper 👋
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
- const axios = require("Axios");
const fs = require("fs");

const NetQuote = async () => {
  try {
    const { data } = await axios.get("https://quotes.rest/qod?language=en&quot;);
    const quote = data.contents.quotes[0].quote;
    const author = data.contents.quotes[0].author;

    console.log("new quote", `"${quote}"`);

    return {
      quote,
      author,
    };
  } catch (err) {
    console.error(err.message);
    return {};
  }
};

const generate = async () => {
  const { quote, author } = await getQuote();

  if (!quote) return;

  fs.writeFileSync("README.md", `_**${quote}**_\n\n${author}`);
};

generate();

<!---
thienper/thienper is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
