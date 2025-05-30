**GSAP**
*GSAP allows you to effortlessly animate anything JS can touch. Delivering silky-smooth performance and unmatched support so you can focus on the fun stuff.*
**Tween**
    
    ### **What's a Tween?**
    
    A [**Tween**](https://gsap.com/docs/v3/GSAP/Tween) is what does all the animation work - think of it like a **high-performance property setter**. You feed in targets (the objects you want to animate), a duration, and any properties you want it to animate and then when the Tween's playhead moves to a new position, figures out what the property values should be at that point applies them accordingly.
    
    ### **Common methods for creating a Tween:**
    
    - [**gsap.to()**](https://gsap.com/docs/v3/GSAP/gsap.to())
    
    The most common type of animation is a **to()** tween because it allows you to define the **destination values** (and most people think in terms of animating ***to*** certain values). For example:
    
    ```jsx
    // rotate and move elements with a class of "box"
    // ("x" is a shortcut for a translateX() transform) over the course of 1 second.
    gsap.to(".box", { rotation: 27, x: 100, duration: 1 });
    ```
    
    - [**gsap.fromTo()**](https://gsap.com/docs/v3/GSAP/gsap.fromTo())
    
    A **`gsap.fromTo()`** tween lets you define **BOTH** the starting and ending values for an animation (as opposed to [**from()**](https://gsap.com/docs/v3/GSAP/gsap.from()) and [**to()**](https://gsap.com/docs/v3/GSAP/gsap.to()) tweens which use the current state as either the start or end). This is great for having full control over an animation, especially when it is chained with other animations. For example:
    
    ```jsx
    //animate ".box" from an opacity of 0 to an opacity of 0.5
    gsap.fromTo(".box", { opacity: 0 }, { opacity: 0.5, duration: 1 });
    ```
    
    - [**gsap.from()**](https://gsap.com/docs/v3/GSAP/gsap.from())
    
    Think of a **`gsap.from()`** like a backwards tween where you define where the values should START, and then it animates to the current state which is perfect for animating objects onto the screen because you can set them up the way you want them to look at the end and then animate in **from** elsewhere. For example:
    
    ```jsx
    // animate ".class" from an opacity of 0 and a y position of 100 (like transform: translateY(100px))
    // to the current values (an opacity of 1 and y position of 0).
    gsap.from(".class", { opacity: 0, y: 100, duration: 1 });
    ```
    
    # Example:
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <link rel="stylesheet" href="./style.css" />
        <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.5/gsap.min.js"></script>
        <title>GSAP</title>
      </head>
      <body>
        <div class="box green"></div>
        <div class="box purple"></div>
        <div class="box blue"></div>
        <script src="./index.js"></script>
      </body>
    </html>
    
    ```
    
    ```css
    body {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      gap: 20px;
    }
    
    .green {
      background: linear-gradient(90deg, #00c9ff 0%, #92fe9d 100%);
      width: 100px;
      height: 100px;
      border-radius: 10px;
    }
    .purple {
      background: linear-gradient(90deg, #fc466b 0%, #3f5efb 100%);
      width: 100px;
      height: 100px;
      border-radius: 10px;
    }
    .blue {
      background: linear-gradient(90deg, #efd5ff 0%, #515ada 100%);
      width: 100px;
      height: 100px;
      border-radius: 10px;
    }
    
    ```
    
    ```jsx
    // gsap.to("className",{animations})
    
    // target the element with a class of "green" - rotate and move TO 100px to the left over the course of 1 second.
    gsap.to(".green", { rotation: 360, x: 500, duration: 5 });
    
    // target the element with a class of "purple" - rotate and move FROM 100px to the left over the course of 1 second.
    gsap.from(".purple", { rotation: -360, x: -100, duration: 1 });
    
    // target the element with a class of "blue" - rotate and move FROM 100px to the left, TO 100px to the right over the course of 1 second.
    gsap.fromTo(".blue", { x: -100 }, { rotation: 360, x: 100, duration: 1 });
    
    ```
