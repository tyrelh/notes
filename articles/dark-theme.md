# Dark Themes
Automatic theme switching based on the visitor's OS preference.

## Intro
I've been obsessed with dark themes for a while now. To the point were I will essentially boycott an app or service if I cannot find a way to theme it dark. Just the thought of staring into a blinding white screen is giving me a headache right now.

Ever since a very early iteration, I have had my personal website styled with a dark theme. But as I get further into my career as a software developer, the thought that anyone but myself might actually look at my website is a looming fear. Is it ready for that? Perhaps in software development this is skewed just a bit but I think in general people prefer the more expected light colours of the internet. Google is light, Amazon is light, nothing popular is dark.

## Theme Switch
I decided to implement a theme switch. After reading a bit into how others accomplished this it turned out to be quite simple. The hard part is developing a light theme for my site.

Essentially all you need to do is create a toggle or checkbox that will apply or remove a class from the HTML `body`. Depending on how your site/app is designed you could apply this class to some other parent component, but since I was using the body background I decided to just use the body.

I built a checkbox based toggle switch. The onClick method will do
```javascript
document.body.classList.toggle("dark-mode");
```

Now, in your CSS, whatever styles you want overridden when this theme is toggled just add the `light-mode` class selector.