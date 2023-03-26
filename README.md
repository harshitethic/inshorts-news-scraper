<h2>Inshorts News Scraper</h2>
<p>I've written a Node.js module that scrapes news articles from the popular news aggregator Inshorts. The module utilizes the cheerio and node-fetch libraries to parse HTML and make HTTP requests, respectively.</p>
<p>I'm Harshit Sharma, also known as <em>harshitehic</em> online.</p>
<h3>Installation</h3>
<p>To use this module in your Node.js project, you can install it via npm:</p>
<pre><code>npm install inshorts-news-scraper</code></pre>
<h3>Usage</h3>
<p>To use this module, you can import it into your Node.js file:</p>
<pre><code>const inshortsScraper = require('inshorts-news-scraper');</code></pre>
<h4><code>getNews</code> function</h4>
<p>The <code>getNews</code> function takes in two arguments: <code>options</code> and <code>callback</code>. <code>options</code> is an object that contains the language and category of the news to be scraped. <code>callback</code> is a function that will be called with the scraped news data and the <code>news_offset</code> parameter (used for pagination).</p>
<pre><code>const options = {
  lang: 'en',
  category: 'national',
};

inshortsScraper.getNews(options, (news, news_offset) =&gt; {
  console.log(news);
  console.log(news_offset);
});
</code></pre>
<h4><code>getMoreNews</code> function</h4>
<p>The <code>getMoreNews</code> function is similar to <code>getNews</code>, but it is used for pagination. It takes in an additional parameter, <code>options.news_offset</code>, which is used to request the next page of news articles. The function sends an HTTP POST request to the Inshorts website with the given options, then scrapes the HTML using <code>cheerio</code> to extract the relevant news data. The scraped data is stored in an array of objects, where each object represents a single news article. The function then calls the <code>callback</code> function with the scraped data and the new <code>news_offset</code> parameter.</p>
<pre><code>const options = {
  lang: 'en',
  category: 'national',
  news_offset: 'jvn36k2y-1',
};

inshortsScraper.getMoreNews(options, (news, news_offset) =&gt; {
  console.log(news);
  console.log(news_offset);
});
</code></pre>
<h3>Author</h3>
<p>This module was written by Harshit Sharma, also known as <em>harshitehic</em> online. You can learn more about him and his work on his website, <a href="https://harshitethic.in/">harshitethic.in</a>.</p>
<h3>License</h3>
<p>This module is licensed under the MIT License.</p>
