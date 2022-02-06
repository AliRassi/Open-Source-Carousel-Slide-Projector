# Open-Source-Carousel-Slide-Projector
Main repo for the development of the Open-Source Carousel Slide Projector

![ezgif com-gif-maker (8)](https://user-images.githubusercontent.com/75351660/152681188-bb001091-4542-4720-a504-375303d6f6d6.gif)
# Background
I always wanted to do an open-source project where I can ask the internet to contribute to its build. I wanted it to be simple enough that would motivate people to help and also challenging enough so that not one person can sit down and do it alone.

During my internship at Formlabs, I’ve regularly met with engineers from other units, and the ones that interested me the most were the optical engineers. I had very little knowledge of optics from back in high school and a little from physics 1 & 2 in college but I went to a couple of their launch and learn meetings where they talked about their R&D and I thought it was so cool.

I kept the open-source project in the back of my mind for a while. About the same time, I went to the Institute of Contemporary Art (ICA) in Boston where my friend was working on the “Figures of Speech” exhibition by Virgil Abloh. Behind the installations and the shop, there was a separate room where there was a tall shelf full of Spike Lee’s books and handouts and BTS materials. There were also two Carousel Slide Projectors that were projecting 35mm slides of behind the scenes of a movie Spike Lee has made for his master thesis. The movie is called Joe's Bed-Stuy Barbershop: We Cut Heads in case you’re wondering. (fun fact: I live in Bed-Stuy!!)

So I was in a room full of all sorts of pictures and books and illustrations, but the only thing that caught my eyes were the slides that were being projected on the wall, one by one, making a distinguished *click* for each slide. And I was not alone! Virtually everyone else in the room was also only watching the slides. And I thought to myself a Carousel Slide Projector is the perfect open-source project!

The mechanism is replicable and very satisfying to watch, the light could be just a high-power LED, it could be powered easily and there is a wide range of people who might want to contribute to its development. Besides, if such a thing is readily available, people will stop printing their pictures which means less ink and paper will be used. Plus once you make a carousel slide projector, you can just swap your pictures and save lots of money not printing.
# Design
To make the project-open source my idea was to work on the carousel myself (indexing mechanism, ejecting the slide, the code, etc.) and ask the internet to design the light projector (the lamp, the cooling system, the lens, etc.) I also wanted to make sure this project, once finished, is accessible to as many people as possible so, from the begging, I decided to make the entire project modular so that people can easily change the parameters to their preferences. I will get into the details of my modularity later.

I wanted my carousel to be rectangular instead of circular so that people with smaller 3D printers could fit the model inside their 3D printers. I used a rack and pinion mechanism to index the slides. The rack is attached to the side of the carousel and the gear is stationary. With the rotation of the gear, the rack will move back and forth. This carousel glides on top of a fixed tray via a dovetail hinge. The carousel is a slotted box that carries the slides in each of those slots. The tray on the other hand only has one slot. When the slot of the carousel coincides with the slot of the tray, the slide will drop down the slot and sit in front of the projector. The groove on the carousel makes it easier to grab your slides when you want to swap them.
![ezgif com-gif-maker (9)](https://user-images.githubusercontent.com/75351660/152681139-39be7b1b-b220-4176-ace9-7cd3f4132722.gif)
As I mentioned I wanted to make this a modular piece so that everyone can adjust it to their taste and still use the project without changing the design. Everything in the project is parametric and could be changed simply by changing the values in the parameters table. Want more slides? Done. Got thicker slides? Done. The tolerance is not enough for your printer? Done.

I really tried to break the model in any possible way and I believe in the current state everything is truly parametric and unbreakable. But of course, for those who want to break it, there will be Github!
![ezgif com-gif-maker (10)](https://user-images.githubusercontent.com/75351660/152681148-17c5e9ac-c5c9-4149-bb71-49f0337536d5.gif)
Regardless of the number of slides you have or the thickness of each one, or any other parameters, the code for advancing to the next slide (or reversing to the previous slide) is the same, which makes the project more easily modifiable and plug-and-play.

The lift lever and the carousel are designed in a way that when the lever pushes the slide up the carousel, the bottom edge of the slide will go above the tray so that it wouldn't get stuck when the carousel advance to the next slide (or reverses to the previous, hence the ramp-to-ramp design.)

![ezgif com-gif-maker (12)](https://user-images.githubusercontent.com/75351660/152681170-da30fe0a-dcb7-45b1-9154-023b14a34599.gif)
![ezgif com-gif-maker (11)](https://user-images.githubusercontent.com/75351660/152681172-ec33b6dc-4f05-45f8-885d-9fc182eca4de.gif)
The servo motor that controls the lift lever, and the stepper motor that moves the carousel are controlled with an Arduino Uno. The servo is mounted on a plate that could move slightly back and forth to fine-tune the position of the lever head according to the hole at the bottom of the tray. This fit has to be tight for the slides to not get stuck in the gap between the tray and lever, and knowing how inaccurate SG90 servo motors are in dimension and performance, I thought it’s best to provide a mechanism that allows you to position your servo based on your tolerances.

The components seem to be floating in the air and that’s because designing a chase for the projector before designing the optics seems unreasonable and most likely it has to change.
