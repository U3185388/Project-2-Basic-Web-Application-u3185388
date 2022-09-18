# Project-2-Basic-Web-Application-u3185388
This is a basic website application developed based on the nuxt framework.
<br>The website program will get the data from "Canberra Modern" and show the relevant content to the user.
## Run the project
Use `cd web-app` on the terminal to locate the root, and choose any way to start hosting:
```
yarn dev
```
or
```
npm run dev
```
## Rationale
In this article I will explain some of the steps and the features of the site. In the entire process of development, I chose VS Code to take my developing help.
### The steps to install nuxt
Type `yarn create nuxt-app` to perform nuxt framework installation.
<br>I pick **JavaScript** as coding language; Then never chose **Testing Framework**, and **continuous integration**; In **Modules**, **Linting tools**, **Development tools**, I have selected everything; In some choices, I chose **Universal Rendering mode**, **Static deployment** and **Git control system**; I used **Bootstrap** in early development, but then I gave up on it.
### Characteristic
According to the logo of "Canberra Modern", I created a pure black navbar; The background of all pages are filled in the same colour order; I also chose "Futura" font, which is as close as possible to the art style of "Canberra Modern".
<br>
#### Navbar
These two are the navbars used on this page. 
<br>**Home page nav**
![nav bar (1)](https://user-images.githubusercontent.com/53715219/190903728-6b68e043-3ff1-484e-a22e-352521439974.png)
<br>**
![nav bar (2)](https://user-images.githubusercontent.com/53715219/190903914-fdae6b6e-f915-4ab8-9d97-8b5973b7f4a5.png)
At first, they were filled with a lot of buttons; but in order to keep the home page alive, I cut out most of the buttons and kept only the necessary three.
<br>
#### Home page
The homepage is styled like a blog site.
![home page](https://user-images.githubusercontent.com/53715219/190903955-8126656e-df52-4dfb-a597-f02367a7046b.png)
 It lists all the slug pages that the homepage can go to.
 <br>
 #### Event/Building page
 They need to fetch data from their respective APIs, so they also design in the style of the homepage.
 <br>**The event page:**
 ![event page](https://user-images.githubusercontent.com/53715219/190904677-b2ed8cf0-f7fd-479f-acee-d6be0f118f69.png)
 <br>**The Building page:**
 ![building page](https://user-images.githubusercontent.com/53715219/190904670-25dc1a8b-6860-43c4-955d-4fafa7b93a88.png)
 The seemingly scattered but revealing neat layout fits the theme of this content.
 <br>
 #### Slug page
 Dynamic pages will grab some key information to fill the content.
 <br>**Building slug page:**
 ![slug page (3)](https://user-images.githubusercontent.com/53715219/190904827-44706e79-e76a-4fc0-a622-66d2241bedd7.png)
 <br>**Home slug page:**
 ![slug page (1)](https://user-images.githubusercontent.com/53715219/190904953-5ade7c50-4f34-42b2-91ee-ffce2050ce52.png)
 <br>**Event slug page:**
 ![slug page (2)](https://user-images.githubusercontent.com/53715219/190904956-b41a90fe-1b6d-49a2-9a26-0145881f2a7f.png)
## Reflection
As I write this document, I can only feel regret.<br>
There have been so many tasks to upload in these two weeks that it was a little too late for me to start this task. Because I know in my heart that I should have done better; the extension of the upload deadline has allowed me to do this project decently, and I am very grateful for that.<br>
During this intense process, I captured some artistic features in advance and showed them on the website to make it look artistic. Because this was my first exposure to frameworks and I had not mastered the language constructs of JavaScript before; this led me to spend a lot of time learning and doing tutorial exercises. Fortunately, the long-term study has given me a certain understanding of most of the nuxt and even vue frameworks.<br>
In this process, the most difficult time should be when you first come into contact with nuxt. The new version brings a lot of file changes, which leads me to always encounter steps that cannot be carried out in my learning; for example, the "Layout" file is removed in the new version (should be placed in the nuxt root directory), which makes I have a huge headache. I even spent some time tweaking Powershell and installing yarn due to issues with my system (that kind of thing that's only available in China always has all sorts of castrations). But these experiences have given me a very clear understanding of each file.<br>
Anyway, although it was a rush, I was quite happy.
