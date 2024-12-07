# Performance and Tuning Web Applications Cheatsheet

## In your backend
- if some information is repeatedly showing in the screen (views) coming from backend from Database, consider adding some cache like Redis or Memcached, so the info cames from the cache and not anymore from querying database
- Nginx can also cache to deliver faster contents 
- If you render views in your backend, you should use a template engine to also generate cached views (like Blade or Twig if you use PHP)
- If you have long processes to run that would take user time, consider use queues (with Redis for example), like email sending, receive webhooks, process payment or generate some personal report from DB
- If you need to frequently send emails, prefer to outsource it to a company that is specialized in this, like SendGrid
- Learn how/why use INDEX on some tables columns (DB), the ones that you do more WHERE's (mainly the ones that are string/varchar variant fields), this will increase SELECT statements response
- If you have lots of queries doing "where \`something\` like '%foobar%' consider use Elastic Search, because this kind of query take more and more time the more the table grows
- Never store file/blobs in your DB, upload it somewhere else. They make the DB and the tables bigger. Your web server can deliver the files and images absurdly faster than querying. You can descentralize using AWS S3, or Backblaze as external file storages
- Learn about BigO Notation and look where your algorithms can be optimized to process faster, like loops inside loops and joins
- Query only the necessary columns you going to use, avoid "SELECT * FROM"
- Never EVER use MongoDB as first option if you don't know why you're choosing it. Most part of the time you are going to need relational databases
- If you going to show html tables or lists full of data in your front end/views, ALWAYS use pagination with limited numbers of results per page
- Never make your backend programming language stream images or videos, this always should be made by the web server, except for very some specific reasons 
- If you use PHP-FPM and NGINX, you can always increase FPM and FastCGI params configs that comes for low end usage, so you can deliver faster/bigger content/requests 
- MySQL also comes default configured for relatively low-end usage, you have to always tune up. Sometimes you might consider using PostgreSQL instead of MySQL
- Never fill/flood your Cookies or Session with unecessary infos, and if you do, unset as soon as you use it
- If you have to frequently generate complex/big reports or graphics, consider having a database clone elsewhere, where you can make complex queries and use the time you want without affect other users
- You can always cache repeated reports generation
- If you have to do some routine that will use a lot of your server processes or memory (some cron job for example), consider looking at Google Analytics to see the best time your website has less users using to make at that time

## For frontend
- Always code Mobile First
- Use Async in your ajax/fetch functions to not break your user experience in the webpage
- Do not request your backend always using ajax/fetch every second, you can flood and make an unintentional DDoS. Consider using websockets, for an event driven approach
- Bundle your assets, always joining, uglifying and minifying CSS and JS files so your code will be drastically smaller, requesting a lot faster to your users
- Learn how to use async/defer in your \<script\> tags to it won't break your user experience waiting for load files
- Try to always put your \<script\> tags at the end of the \<body\> tag, right before \</body\>
- Always put your CSS inside the \<head\> tags 
- NEVER use REACTIVE libs/frameworks if your problem does not requires reactivity to solve. Sometimes reactive code increase 2-10x more the size of your JavaScript code
- NEVER use experimental/beta Objects, properties or functions in your JavaScript. If if doubt, search the MDN to see if it is widely accepted by the browsers. Consider using polyfills, or Babel if you must (with the trade off being a higher bundle size)

## Architectural Related
- Always use frameworks that follows SOLID and that implements design patterns, so you can avoid performance problems like the Banana-Gorilla-Jungle problem and decrease unused things in your server's memory and process less
- Before start a project, think and discuss with your team the right architecture to implement. Sometimes MVC and/or Microservices aren't the better to follow. There are plenty of others architecture types
- Refactor your code always you can, so can be more testable, avoid duplication and avoid losing lots of programming hours. 
- Aways use Cloudflare (that has a free plan) or some similar group of services that can cache and have a fast DNS around the world to deliver fast requests

---
### Tips

- Avoid global variables whenever possible. This will make your code use less memory.
- Avoid loops inside loops, there are usually ways to do what you want without creating a O(n²) algorithm
- [NewRelic](https://newrelic.com/) is one of the best free tools you can use to see where are the performance issues in your web application. Consider installing it in your server if need it. Sometimes this tool is a life-changer.
- If you use Laravel (PHP), consider adding [Laravel Debugbar](https://github.com/barryvdh/laravel-debugbar) to your project. It can help you with query issues and slow responses
- AWS have a lot of tools and services that can outsource your problems to their servers to process, log and store, which are already tuned most of the time
- If you read all this guide and paid attention, you could see most of the "optimization" issues can be solved by: caching, queuing, oursourcing and optimizing algorithms. It is purely science, not magic. Using the right service for the right job, using the right tool to solve the right problem.
