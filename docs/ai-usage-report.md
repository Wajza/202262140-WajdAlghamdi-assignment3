# AI Usage Report

---

## AI Tools Used & Use Cases

**ChatGPT (GPT-4):**
- **API Integration (GitHub):** AI generated the basic fetch pattern and error handling for the GitHub API, and I added a retry button, user-friendly error messages, a loading spinner, and dynamic language filter population that extracts unique languages directly from the fetched repository data.

- **Complex Logic (Filter + Sort):** AI suggested using filter() and sort() array methods, and I implemented combined filter+sort that works together with debouncing to prevent excessive DOM updates when users change dropdown options.

- **Complex Logic (Quiz):** AI provided a basic quiz structure, and I customized all 3 questions for developer paths (frontend, backend, fullstack, problem-solver), added a progress bar, stored results in localStorage, and created personalized recommendations for each result.

- **State Management:** AI explained localStorage and sessionStorage patterns, and I implemented a persistent visit counter, a real-time session timer with minutes and seconds, theme preference saving, and quiz result storage.

- **Performance:** AI recommended lazy loading and debouncing, and I implemented Intersection Observer for skill bar animations, debounced filter/sort events, lazy loading for images, and prefers-reduced-motion support.


---

## Benefits & Challenges

**Benefits:**
- **Time Efficiency:** Using AI reduced my development time by approximately 60-70%, allowing me to complete all Assignment 3 features (GitHub API integration, interactive quiz, filter and sort functionality, stats bar with visit counter and session timer) in about 4 hours instead of 10+ hours from scratch.

- **Learning Accelerator:** AI helped me understand how to fetch live data from GitHub's REST API using async/await, how to use localStorage for persistent visit counting and theme preference, how to implement sessionStorage for a real-time session timer, and how to combine filter and sort logic using array methods.

- **Code Quality:**	AI suggested best practices like debouncing the filter and sort dropdowns to prevent excessive DOM updates, adding loading spinners while fetching GitHub repos, implementing retry buttons for API failures, and using semantic HTML with ARIA labels for accessibility.

- **Problem Solving:** When my filter and sort combination wasn't working together (filtering by language then sorting by stars), AI helped me understand that the order of operations matters. When my quiz result wasn't displaying correctly, AI pointed out that I needed to count answer types properly. When my session timer wasn't updating in real-time, AI explained how to use setInterval correctly.

- **Documentation:** AI provided templates for the AI Usage Report and technical documentation, which I customized with my specific learning outcomes, the actual features I implemented (GitHub API with my username Wajza, quiz with 3 developer path questions, stats bar with visit counter), and detailed modifications I made to AI-generated code.

**Challenges and Limitations:**
- **Context Understanding:** AI did not always understand my existing portfolio structure, so when it generated code for the GitHub section, I had to manually adjust the CSS classes to match my existing color variables (--primary-color, --bg-color) and dark mode theme.

- **Code Accuracy:**  AI once generated a filter function that referenced a variable repos that didn't exist in that scope, and another time generated a quiz progress calculation that was off by one question, forcing me to test every feature in my browser before considering it working.

- **Generic Solutions:** AI provided generic placeholder content like "Repository description goes here" and quiz questions about "favorite programming language," which I rewrote to display actual GitHub repo descriptions and to focus on development preferences (frontend, backend, fullstack, problem-solver).

- **Image Path Issues:** AI consistently used generic paths like "profile.jpg" and "project.png," but my actual portfolio uses assets/images/PFP.png, assets/images/KSIH.png, assets/images/EBS.png, and assets/images/KE.png, requiring me to manually update every single image path in the HTML.

- **Over-reliance Risk:**  I made a rule to never use AI-generated code unless I could explain what each line does, which meant studying complex concepts like debouncing, Intersection Observer, and the GitHub API response structure until I fully understood them before implementation.

---

## Learning Outcomes

**Technical Skills Gained:**
- **GitHub REST API Integration:** Learned to fetch live repository data from https://api.github.com/users/Wajza/repos using async/await, parse the JSON response, extract unique programming languages for the filter dropdown, and display repo names, descriptions, stars, forks, and language badges.

- **Combined Filter + Sort Logic:** Learned that filtering (by language) and sorting (by stars, name, or recent updates) must work together in the correct order—filter first, then sort the filtered results—to produce accurate results.

- **localStorage for Persistent Data:** Learned to save the visit counter so it increments across browser sessions, save the user's theme preference (dark/light mode), and store quiz results with timestamps so users can see their previous result.

- **sessionStorage for Session Data:** Learned to track how long a user stays on my site with a real-time timer that updates every second, storing the start time in sessionStorage so the timer doesn't reset on page refresh but does reset when the browser tab closes.

- **Debouncing for Performance:** Learned to add a 300ms delay to the filter and sort dropdowns so the repos only re-render after the user stops interacting, preventing unnecessary DOM updates when options are changed rapidly.

- **Intersection Observer for Scroll Animations:** Learned to animate the skill progress bars only when they become visible in the viewport, improving performance by not animating elements the user hasn't seen yet.

- **Error Handling for API Calls:** Learned to wrap API calls in try/catch blocks, display user-friendly error messages instead of console errors, and provide a retry button that lets users attempt to fetch the repos again. 

**Key Technical Concepts Learned:**
- **API Integration:** I can now fetch data from external APIs, handle loading states with spinners, display the data dynamically, and handle errors gracefully when the API fails or the user is offline.

- **Filter + Sort Together:** I learned that filter and sort need to be combined carefully—sorting first then filtering gives different (often wrong) results, so I always filter first, then sort the filtered array.

- **localStorage vs sessionStorage:** localStorage persists forever until manually cleared (perfect for total visit count and theme preference), while sessionStorage only lasts for the current browsing session (perfect for session timers and temporary state).

- **sessionStorage for Session Data:** Learned to track how long a user stays on my site with a real-time timer that updates every second, storing the start time in sessionStorage so the timer doesn't reset on page refresh but does reset when the browser tab closes.

- **Debouncing:** I learned that without debouncing, every dropdown change triggers a full re-render, which slows down the page. With debouncing, the function only runs after the user pauses for 300ms.

- **Quiz Logic with Weighted Scoring:** I learned to track user answers in an array, count the frequency of each answer type, and determine the dominant type to display the correct result.

**Workflow Improvements:**

- **Before AI:**
When I encountered an error, I would panic and randomly change code hoping it would work, often creating new bugs. I would spend hours searching Stack Overflow, copy-pasting solutions I didn't fully understand, just to move on to the next problem. This trial-and-error approach wasted time and left me with knowledge gaps.

- **After AI:**
AI transformed my workflow into a systematic learning process. Now when I hit an error, I copy the exact message and ask AI to explain what's wrong. I learn the root cause, get solutions with clear explanations, implement them myself, and document what I learned. This approach has cut my debugging time by 75% and turned every problem into a learning opportunity that builds my skills and confidence.

---

## Responsible Use & Modifications

For every AI-generated suggestion, I followed this review process:
1. **Generate** → Get AI suggestion
2. **Analyze** → Understand what the code does
3. **Test** → Run in browser to verify functionality
4. **Modify** → Customize for my specific needs
5. **Improve** → Add error handling, comments, optimizations

**Specific Modifications Made:**
| AI-Generated | Why I Changed It |
|--------------|-------------------|
| Generic GitHub username "octocat" | Match my actual GitHub account |
| Basic fetch without error handling | Prevent crashes when API fails |
| Hardcoded language filter options | Need dynamic options from API data |
| Simple filter and sort separately | 	Need them to work together |
| Generic quiz questions about "favorite language" | Need developer path questions |
| Basic quiz result calculation | Need accurate weighted scoring |
| No quiz progress bar | Need visual feedback for users |
| No visit counter | Requirement for state management |
| No session timer | Requirement for state management |
| No debouncing on filters | Performance issues with rapid changes |
| No Intersection Observer for skills | Animations run even when not visible |
| Generic image paths like "profile.jpg" | Match my actual folder structure |
| Basic form validation (empty check only) | Need better user experience |
| No loading states for form submission | Users could submit multiple times |
| Simple theme toggle without animation | Need more polished appearance |
| No localStorage for theme preference | Theme resets on page refresh |

**Academic Integrity Statement:**
I confirm that:
- ✅ All AI-generated code was reviewed and modified
- ✅ I understand every line of code in this project
- ✅ AI was used as a learning tool, not a replacement
- ✅ All content accurately represents my work and identity
- ✅ Image paths were corrected to match my folder structure
- ✅ All personal information (name, ID, contact) is accurate