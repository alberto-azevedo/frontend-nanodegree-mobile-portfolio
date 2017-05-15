## Website Performance Optimization portfolio project

This is my  Website Performance Optimization, the goal is improve the PageSpeed
score, for index.html and the fps mark of pizza.html scrool.

To run: clone the repo and execute:
cd /path/to/your-project-folder
python -m http.server 8080 (obs.: python3)

#### Part 1: Optimize PageSpeed Insights score for index.html
1. Created google_analytics() in analytics.js, and calling it after page load.

2. Loading some scripts assyncrony:
<script src="http://www.google-analytics.com/analytics.js" async></script>
<script async src="js/perfmatters.js"></script>
<script async src="js/analytics.js"></script>

3. Removing high overhead font load

4. Inlinning print and style css files.

#### Part 2: Optimize Frames per Second in pizza.html

Changes to optimise:

1. Add "backface-visibility: hidden" and "will-change: left" to ".mover" in views/css/style.css

2. determineDx now calls sizeSwitcher avoiding expensive calculation of pizza size.

3. changePizzaSizes is avoiding access of style properties in loop.

4. updatePositions changed main loop to avoid recalculation of phase. Using leftsArray, initialized on DOMContentLoaded. Removed all access to style properties, changed for variables ou constants.

### Optimization Tips and Tricks
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>
