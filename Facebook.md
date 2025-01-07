<!-- System Design -->

1. Requirements (Functional and Non-Functional)
2. High level Architecture
3. Data model (Client)
4. API Model (HTTP Protocol)
5. Optimizations / Performance.

case study - Facebook News Feed

1. REQUIREMENTS

   1. Functional -
      a. Feed that displays a list of items
      b. Feed that can include comments
      c. User post type
      d. Infinite scrolling (How many feeds do you want to display per viewport).

   2. Non-Functional
      a. Mobile responsiveness
      b. Offline mode. (Nice to have) (PWA)
      c. Accessibility friendly (a11y)
      d. Internationalization support (nice to have)
      e. Should be performant (Have a good latency)
      f. Expected volume for observability estimation (Napkin math).

2. HIGH LEVEL ARCHITECTURE
   a. start with a simple UI
   b. Design the component architecture.
   c. Discuss the design patterns you want to use and why
   e. Explain data flow
   f. explain interactivity.

Design Pattern -- Model-View-Controller (MVC)
![screenshot](/Assets/Screenshot%202024-12-23%20at%2008.48.30.png)

The MVC pattern divides an application into three interconnected components, enabling separation of concerns.

    Model: Manages the data, logic, and business rules of the application. It is responsible for fetching and updating data, often interacting with a database or API.
    View: The user interface of the application. It displays data from the model to the user and sends user interactions to the controller.
    Controller: Handles user input and updates the model or view accordingly. It acts as a bridge between the model and the view.

    Model: API calls or local state management in frameworks like React.
    View: React components, Angular templates, or HTML.
    Controller: Functions that handle events and update the state or DOM.

3. DATA MODEL - App = {
   feed:Feed
   }
   Feed:{
   item:List[ListFeeds]
   page,
   size
   }
   ListFeeds:{
   type:FeedItemType
   author
   content,
   comment:List[FeedItemComments]
   }

4. API DESIGN - HTTP1 VS HTTP2
   ![screenshot](/Assets/Screenshot%202024-12-23%20at%2010.25.54.png)

   API OPTIONS
   Polling/REST API - (Simple, load balance)
   GRAPHQL - (Pull the data you need and type safety)
   WEB SOCKET - (Bidirectional, Speed, pull data that you need)

5. PERFORMANCE
   Compression headers (GZIP, BROTLI)
   Caching (e.g Apollo Caching)
   Batching Requests (Group request if it's possible)
   Image Optimization
   Bundle Splitting

6. RENDERING
   client rendering
   server rendering
   responsiveness
   Lazy imports
   SEO (TTI, CLS, FCP)

7. ACCESSIBILITY
   HTML5 Semantic tags,
   ARIA roles
   REM font sizes
   Proper contrast
   keyboard navigation

8. SECURITY
   CORS
   XSS
   Rate Limiting
