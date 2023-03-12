# Cute scroll 

Beautiful [scroll](https://8panteon8.github.io/cutescrole/) for clear css and java script whit use [gsap](https://greensock.com/gsap/) 


Padding and margin calculate 


## Features
- Сustom design 
- Parallax
- Animations
- Soft scrolling
- Adaptation for all screens


## References
- [Gsap](https://greensock.com/gsap/)
- [Bootstrap-breakpoint](https://getbootstrap.com/docs/4.6/getting-started/introduction/)


# Use with React
```jsx
const main = useRef();

useLayoutEffect(() => {
  const ctx = gsap.context(() => {
    ScrollSmoother.create({
      smooth: 1.5,
      effects: true,
    });

  }, main);
  return () => ctx.revert();
}, []);

const left = useRef();

useLayoutEffect(() => {
  const ctx = gsap.context((self) => {
    const boxes = self.selector(".gallary__left .gallery__item");
    boxes.forEach((item) => {
      gsap.fromTo(
        item,
        {
          opacity: 0,
          x: -100,
        },
        {
          opacity: 1,
          x: 0,
          scrollTrigger: {
            trigger: item,
            start: "-850",
            end: "-100",
            scrub: true,
          },
        }
      );
    });
  }, left); // <- Scope!
  return () => ctx.revert(); 
}, []);

return (
  <div id="smooth-wrapper" ref={main}>
    <div id="smooth-content">
      <You components ref={left}/>
    </div>
  </div>
);
```




## Screenshot

![ezgif com-video-to-gif-2](https://user-images.githubusercontent.com/113831614/223164395-544dc330-be11-4e66-9df3-a409b3997784.gif)
