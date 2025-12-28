# Blog Post Template Guide

## How to Create a New Blog Post

1. **Create a new HTML file** in the `/blog/` directory
   - Name it descriptively (e.g., `building-local-rag-systems.html`)
   - Use hyphens for spaces, all lowercase

2. **Copy this template structure:**

```html
<!DOCTYPE html>
<html lang="en" class="">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  
  <title>Your Article Title | Mohammad Deen Hayatu</title>
  <meta name="description" content="Brief description of your article (150-160 characters)" />
  <meta name="keywords" content="keyword1, keyword2, keyword3" />
  
  <!-- Open Graph -->
  <meta property="og:title" content="Your Article Title" />
  <meta property="og:description" content="Article description" />
  <meta property="og:type" content="article" />
  <meta property="article:published_time" content="2025-12-28" />
  <meta property="article:author" content="Mohammad Deen Hayatu" />
  
  <link rel="canonical" href="https://deen-hayatu.github.io/blog/your-article-slug.html" />
  <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>💻</text></svg>" />
  
  <script>tailwind = { darkMode: 'class' }</script>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="../assets/css/components.css" />
  
  <!-- Syntax Highlighting (optional) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/github-dark.min.css">
  <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/highlight.min.js"></script>
</head>

<body class="bg-gray-50 text-gray-900 dark:bg-gray-900 dark:text-gray-100">

<!-- NAV -->
<nav class="nav">
  <div class="nav-inner">
    <a href="../index.html" class="nav-logo">Mohammad Deen Hayatu</a>
    <div class="nav-links desktop-nav">
      <a href="../index.html">Home</a>
      <a href="../index.html#projects">Projects</a>
      <a href="index.html">Blog</a>
      <a href="../index.html#contact">Contact</a>
    </div>
    <button id="themeToggle" class="btn"><span id="themeText">Dark</span></button>
  </div>
</nav>

<!-- ARTICLE -->
<article class="section bg-white dark:bg-gray-900">
  <div class="container max-w-3xl">
    <!-- Article Header -->
    <header class="mb-8">
      <div class="flex items-center gap-3 mb-4">
        <span class="px-3 py-1 bg-purple-100 dark:bg-purple-900 text-purple-700 dark:text-purple-300 rounded-full text-sm font-semibold">
          Category
        </span>
        <span class="text-gray-500">5 min read • Dec 28, 2025</span>
      </div>
      
      <h1 class="text-4xl md:text-5xl font-bold mb-4" style="background: linear-gradient(135deg, #667eea 0%, #14b8a6 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">
        Your Article Title
      </h1>
      
      <p class="text-xl text-gray-600 dark:text-gray-300 leading-relaxed">
        A compelling subtitle or introduction paragraph that hooks the reader.
      </p>
      
      <div class="flex items-center gap-4 mt-6 pt-6 border-t border-gray-200 dark:border-gray-700">
        <img src="../assets/images/profile.jpg" alt="Mohammad Deen Hayatu" class="w-12 h-12 rounded-full" />
        <div>
          <div class="font-semibold">Mohammad Deen Hayatu</div>
          <div class="text-sm text-gray-500">Software Engineer & AI Developer</div>
        </div>
      </div>
    </header>

    <!-- Article Content -->
    <div class="prose prose-lg dark:prose-invert max-w-none">
      <h2>Section Heading</h2>
      <p>Your content here...</p>
      
      <h3>Subsection</h3>
      <p>More content...</p>
      
      <pre><code class="language-javascript">
// Code example
const example = "hello world";
      </code></pre>
      
      <blockquote>
        <p>Important quote or callout</p>
      </blockquote>
      
      <ul>
        <li>List item 1</li>
        <li>List item 2</li>
      </ul>
    </div>

    <!-- Article Footer -->
    <footer class="mt-12 pt-8 border-t border-gray-200 dark:border-gray-700">
      <div class="flex flex-wrap gap-2 mb-6">
        <span class="text-sm text-gray-600 dark:text-gray-400">Tags:</span>
        <span class="px-3 py-1 bg-gray-100 dark:bg-gray-800 rounded-full text-sm">Tag1</span>
        <span class="px-3 py-1 bg-gray-100 dark:bg-gray-800 rounded-full text-sm">Tag2</span>
      </div>
      
      <div class="text-center py-8 bg-gradient-to-br from-purple-50 to-teal-50 dark:from-gray-800 dark:to-gray-900 rounded-lg">
        <h3 class="text-2xl font-bold mb-2">Enjoyed this article?</h3>
        <p class="mb-4">Follow me for more insights on software engineering and AI</p>
        <div class="flex justify-center gap-4">
          <a href="https://twitter.com/Deen_Hayatu" class="link">Twitter/X</a>
          <a href="https://github.com/Deen-Hayatu" class="link">GitHub</a>
          <a href="https://www.linkedin.com/in/mohammad-deen-hayatu-895846156" class="link">LinkedIn</a>
        </div>
      </div>
    </footer>
  </div>
</article>

<!-- Related Articles (optional) -->
<section class="section bg-gray-50 dark:bg-gray-800">
  <div class="container max-w-5xl">
    <h2 class="text-2xl font-bold mb-6">Related Articles</h2>
    <div class="grid md:grid-cols-2 gap-6">
      <!-- Add related article cards here -->
    </div>
  </div>
</section>

<footer class="footer">© 2025 Mohammad Deen Hayatu</footer>

<script>
  // Theme toggle
  const toggle = document.getElementById("themeToggle");
  const themeText = document.getElementById("themeText");
  const html = document.documentElement;
  const currentTheme = localStorage.getItem("theme") || "light";
  
  if (currentTheme === "dark") {
    html.classList.add("dark");
    themeText.textContent = "Light";
  }
  
  toggle.onclick = () => {
    html.classList.toggle("dark");
    themeText.textContent = html.classList.contains("dark") ? "Light" : "Dark";
    localStorage.setItem("theme", html.classList.contains("dark") ? "dark" : "light");
  };
  
  // Syntax highlighting
  if (typeof hljs !== 'undefined') {
    hljs.highlightAll();
  }
</script>

</body>
</html>
```

## Tailwind Prose Classes

For article content styling, use these classes on your content wrapper:
- `prose` - Base typography styles
- `prose-lg` - Larger text
- `dark:prose-invert` - Dark mode support
- `max-w-none` - Remove max width restriction

This gives you:
- Beautiful typography
- Proper heading hierarchy
- Code block styling
- Blockquote styling
- List styling
- Link styling

## Tips for Great Blog Posts

1. **SEO-Friendly Titles**: Include main keywords
2. **Meta Description**: 150-160 characters, compelling
3. **Keywords**: 5-8 relevant keywords
4. **Images**: Use descriptive alt text
5. **Code Blocks**: Use syntax highlighting
6. **Internal Links**: Link to your projects
7. **CTA**: Call-to-action at the end
8. **Reading Time**: Calculate based on ~200 words/minute

## Publishing Checklist

- [ ] Proofread for typos
- [ ] Test all links
- [ ] Test code examples
- [ ] Check mobile responsiveness
- [ ] Verify dark mode works
- [ ] Update blog index with new post
- [ ] Update sitemap.xml with new URL
- [ ] Share on social media
