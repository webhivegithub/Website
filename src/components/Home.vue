<script>
  export default {
    name: 'App',
    
    data() {
      return {
        currentIndex: 0,
        reviewcards: [
        {
          name: "Antoine Leth",
          content: "Bought the package course not really knowing what I expect, but I was pleasantly surprised...",
          stars: [1, 2, 3, 4, 5]
        },
        
        {
          name: "Anonymous",
          content: "I'm a mum and I wanted to explore different career paths. I found a few courses online but settled on WebHive. I feel like I know more than my son now haha!",
          stars: [1, 2, 3, 4, 5]
        },
        
        {
          name: "Tim Rock",
          content: "I am currently a backend developer but wanted to be a full stack developer. I bought the package course and honestly i wasn't disapointed. Everything was so clear and concise. Will most likely purchase another course soon. Thanks.",
          stars: [1, 2, 3, 4, 5]
        },
        
        {
          name: "Muhammad",
          content: "I am student and dont have a lot of money. I contacted WebHive and they assisted me in which course would be the best for me. I purchased the javascript course. Thanks WebHive.",
          stars: [1, 2, 3, 4]
        },
        
        {
          name: "Josh Humand",
          content: "Great communication and great education.",
          stars: [1, 2, 3, 4, 5]
        },
        
        {
          name: "Spencer Hill",
          content: "I am struggling with my univeristy web developing module at the moment so my parents bought the html and css course from WebHive to help me and in the end i passed with a first! Thank you.",
          stars: [1, 2, 3, 4, 5]
        }
        ],
        
        loginform: false,
        showextended: false,
        hidebanner: false,
        showcontact: true,
        morebanner: true,
        save: false,
        save2: false,
        save3: false,
        save4: false,
        save5: false,
        save6: false
      };
    },
    methods: {
      ScrollIntoView() {
        const reviewcards = document.querySelectorAll(".reviewcards"),
        currentCard = reviewcards[this.currentIndex],
        container = document.getElementById("expand-words"),
        containerRect = container.getBoundingClientRect(),
        currentCardRect = currentCard.getBoundingClientRect(),
        currentCardLeft = currentCardRect.left,
        containerLeft = containerRect.left,
        currentCardWidth = currentCardRect.width,
        containerWidth = containerRect.width,
        currentCardCenter = currentCardLeft + currentCardWidth / 2,
        containerCenter = containerLeft + containerWidth / 2,
        distanceToMove = currentCardCenter - containerCenter,
        scrollLeft = container.scrollLeft,
        finalScroll = scrollLeft + distanceToMove;
        container.scrollTo({
          left: finalScroll,
          behavior: "smooth"
        });
      },
      forwardbutton() {
        if (this.currentIndex < this.reviewcards.length - 1) {
          this.currentIndex++;
          
          this.ScrollIntoView();
        }
      },
      backbutton() {
        if (this.currentIndex > 0) {
          this.currentIndex--;
          
          this.ScrollIntoView();
        }
      },
      isElementInViewport(element) {
        const rect = element.getBoundingClientRect();
        return (
        rect.top >= 0 && rect.left >= 0 && rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) && rect.right <= (window.innerWidth || document.documentElement.clientWidth)
        );
      },
      handleScroll() {
        const middletitle = document.getElementById("middle-title");
        
        if (this.isElementInViewport(middletitle)) {
          middletitle.style.transition = "transform 0.5s ease-in-out";
          middletitle.style.transform = "rotate(-17deg)";
          
          document.addEventListener("mousemove", (event) => {
            middletitle.style.transition = "transform 0s ease-in-out";
            
            const cursorX = event.clientX,
            cursorY = event.clientY,
            middletitleRect = middletitle.getBoundingClientRect(),
            middletitleX = middletitleRect.left + middletitleRect.width / 2,
            middletitleY = middletitleRect.top + middletitleRect.height / 2,
            distanceX = cursorX - middletitleX,
            distanceY = cursorY - middletitleY,
            angle = Math.atan2(distanceY, distanceX),
            radius = 50,
            moveX = (middletitleX + radius * Math.cos(angle) - cursorX) * 0.04,
            moveY = (middletitleY + radius * Math.sin(angle) - cursorY) * 0.04;
            
            middletitle.style.transform = `translate(${moveX}px, ${moveY}px) rotate(-17deg)`;
          });
        }
      },
      
      toggleNav() {
        const nav = document.getElementById("nav-icon3");
        nav.classList.toggle("open");
      }
    },
    
    mounted() {
      window.addEventListener("scroll", handleScroll);
      
      function handleScroll() {
        const nav = document.querySelector('nav'),
        codedin = document.querySelector('.codedin'),
        icon = document.querySelector('.icon'),
        isScrollingUp = window.scrollY < 1;
        
        nav.classList.toggle('ActiveScrollNav', !isScrollingUp);
        nav.classList.toggle('NotActiveScrollNav', isScrollingUp);
        
        codedin.classList.toggle('ActiveScrollCodedin', !isScrollingUp);
        codedin.classList.toggle('NotActiveScrollCodedin', isScrollingUp);
        
        icon.classList.toggle('ActiveScrollIcon', !isScrollingUp);
        icon.classList.toggle('NotActiveScrollIcon', isScrollingUp);
      }
      
      document.querySelector('.codingvideo').playbackRate = 3;
    }
  }
</script>

<template>
  <div id="app">
    <aside v-if="loginform" class="loginform fixed right-4 z-20 mt-32 rounded shadow-lg shadow-black bg-white w-[350px]">      
      <form class="w-full h-full flex flex-col justify-center items-center pb-10 pt-10">
        <div class="flex items-center rounded-t-sm p-4 text-[#ffffff] w-full -mt-20 z-10 mb-10 h-[60px] bg-custom-blue">
          <h2 class="icon">WebHive - log in</h2>
          <button class="w-6 h-6 absolute right-4 z-20" @click="loginform = !loginform">
            <img class="w-full h-full" src="../assets/images/x.png" alt="">
          </button>
        </div>
        
        <input class="w-[80%] h-[40px] mt-4 p-2 rounded-lg outline-custom-blue border-[1px] textboxes border-[#888888]" type="text" placeholder="Email">
        <input class="w-[80%] h-[40px] mt-4 p-2 rounded-lg outline-custom-blue border-[1px] textboxes border-[#888888]" type="text" placeholder="Password">
        <button class="w-[80%] h-[40px] mt-4 p-2 rounded-lg bg-custom-blue text-white font-semibold">Log in</button>
        <button class="flex items-center justify-center h-[25px] mt-2 p-2 rounded text-[#222222] font-semibold">Sign up</button>
      </form>
    </aside>
    
    <aside v-if="!hidebanner" class="w-full py-2 bg-custom-blue text-white flex items-center codedin duration-150 pr-10">
      <p class="pl-4 font-light sm:text-sm text-[13px]">This website was fully coded by WebHive using <a class="underline" href="https://vuejs.org/" target="_blank">Vue</a> and <a class="underline" href="https://tailwindcss.com/" target="_blank">Tailwind</a>, accompanied by <a class="underline" href="https://sass-lang.com/" target="_blank">SCSS</a>.</p>
      
      <div class="absolute right-4 flex flex-col sm:flex-row gap-2">
        <img @click="morebanner = !morebanner" class="w-4 right-8 cursor-pointer" src="../assets/images/questionmark.png" alt="">
        <img @click="hidebanner = !hidebanner" class="w-4 right-2 cursor-pointer" src="../assets/images/x.png" alt="">
      </div>
    </aside>
    
    <div v-if="!morebanner" class="bg-custom-blue absolute right-10 top-16 z-20 text-white w-[400px] p-4 rounded-lg">
      <img class="absolute right-2 -top-3" src="../assets/images/toparrow.png" alt="">
      
      <h2 class="font-bold text-[16px] bg-[#111111] mb-10 p-2 text-center rounded">See more about how WebHive was coded</h2>
      <ul class="text-[15px]">
        <li><span class="font-bold underline">Vue</span><br>WebHive was coded in Vue, setup by vite. Multiple pages were used in this website so vue components were perfect.</li><br>
        <li><span class="font-bold underline">Tailwind</span><br>The styling of WebHive is all thanks to tailwind, which allowed me to quickly and efficiently style the pages.</li><br>
        <li><span class="font-bold underline">SCSS or SASS</span><br>This css extension enabled me to nest rules.</li><br>
      </ul>
    </div>
    
    <nav class="duration-150 fixed bg-[#0d0d0dcf] z-10  text-white w-full flex items-center font-semibold py-5">
      <a href="" class="icon labelsclass sm:left-5 sm:text-lg text-sm left-2 text-white absolute cursor-pointer">WebHive</a>
      
      <div @click="toggleNav" class="block md:hidden" id="nav-icon3">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
      </div>
      
      <!-- <div class="hidden md:flex"> -->
        <div class="hidden md:flex mx-auto navlinks pl-32">
          <a class="sm:mx-2 mr-1 cursor-pointer">Home</a>
          <a class="sm:mx-2 mx-1 cursor-pointer">Courses</a>
          <a class="sm:mx-2 mx-1 cursor-pointer">Course info</a>
          <a class="sm:mx-2 mx-1 cursor-pointer">About</a>
          <a @click="showcontact = !showcontact" class="sm:mx-2 mx-1 cursor-pointer">Contact</a>
        </div>
        
        <button class="hidden md:flex mr-6" href="">Basket 
          <img class="w-4 h-4 ml-1 mt-[3px]" src="../assets/images/basket-white.png" alt="login">
        </button>
        <button @click="loginform = !loginform" class="hidden md:flex loginbutton" href="">Log in 
          <img class="w-3 h-3 mr-2 ml-1 mt-1.5" src="../assets/images/login.png" alt="login">
        </button>
        <!-- </div> -->
      </nav>
      
      <header class="h-[400px] sm:h-[550px] w-full bg-[#111111]">
        <div class="absolute sm:left-16 sm:top-[250px] top-[190px] -left-6 scale-[85%] sm:scale-[1.10] text-white pb-14 w-[500px] max-w-md p-4 rounded-lg duration-200">
          <h1 class="text-[50px] font-semibold leading-[55px]">Learn to code websites</h1>
          <p class="opacity-60 text-[15px] mt-2 w-full">Learn how to make websites through coding HTML, CSS, and JavaScript. Additionally, master your design skills and learn frameworks. <span v-if="showextended"> Learn Tailwind, SCSS, and Vue js, key features of front end web development if you want to broaden your skills and advance your websites. </span>
            <button @click="showextended = !showextended" class="text-white font-bold underline">
              See <span v-if="showextended">less</span><span v-else>full</span>
            </button>
          </p>
          
          <div class="flex w-full mt-4">
            <a href="#scrolltocourses" class="bg-custom-blue text-[13.5px] font-semibold w-[135px] h-[40px] text-left pl-3 flex items-center cursor-pointer">LEARN NOW 
              <img class="w-5 ml-2" src="../assets/images/learnmorearrow.png" alt="">
            </a>
            <a class="bg-transparent text-[13.5px] flex items-center justify-center font-semibold w-[135px] h-[40px] text-center border-[1px] ml-4 cursor-pointer">FIND OUT MORE</a>
          </div>
        </div>
        
        <video autoplay muted playsinline loop class="w-full object-cover h-full loadingvideo">
          <source src="../assets/videos/1two.mp4" type="video/mp4">
        </video>
        
        <div v-if="!showcontact" class="contactsection pointer-events-none rounded-2xl bg-[#000000f2] w-[400px] h-[450px] fixed right-6 z-10 top-20 grid-cols-2 place-content-center">
          <div class="w-[130px] h-full left-0 absolute bg-[#222222c0] rounded-l-xl contactbuttonsection">
            <h2 class="text-white text-2xl font-semibold ml-6 mt-4">Find us</h2>
            
            <div class="grid grid-rows-5 grid-cols-1 place-items-center gap-2 mt-6 w-full">
              <div class="h-16 rounded-full w-[64px] bg-[#222222] childdiv hover:cursor-pointer">
                <img class="mix-blend-lighten w-10 ml-3 mt-3" src="../assets/images/facebook.png">
              </div>
              <div class="h-16 rounded-full w-[64px] bg-[#222222] childdiv hover:cursor-pointer">
                <img class="mix-blend-lighten w-10 ml-3 mt-3" src="../assets/images/tiktokwhite.png">
              </div>
              <div class="h-16 rounded-full w-[64px] bg-[#222222] childdiv hover:cursor-pointer">
                <img class="mix-blend-lighten w-10 ml-3 mt-3" src="../assets/images/insta.png">
              </div>
              <div class="h-16 rounded-full w-[64px] bg-[#222222] childdiv hover:cursor-pointer">
                <img class="mix-blend-lighten w-10 ml-3 mt-3" src="../assets/images/git.png">
              </div>
              <div class="h-16 rounded-full w-[64px] bg-[#222222] childdiv hover:cursor-pointer">
                <img class="mix-blend-lighten w-10 ml-3 mt-3" src="../assets/images/twi.png">
              </div>
            </div>
          </div>
          
          <div class="w-[250px] h-full absolute right-[9px] rounded-r-xl formsection">
            <h2 class="text-white text-2xl font-semibold ml-6 mt-4">Write to us</h2>
            
            <form class="grid place-items-center" action="https://api.staticforms.xyz/submit" method="post">
              <input class="bg-[#222222] text-white rounded w-[90%] mt-6 h-11 p-2" type="text" name="name" placeholder="Your Name">
              <input class="bg-[#222222] text-white rounded w-[90%] mt-6 h-11 p-2" type="text" name="email" placeholder="Your Email" />
              <textarea placeholder="Message" class="bg-[#222222] text-sm w-[90%] rounded text-white mt-6 h-32 max-h-32 min-h-32 p-2" name="message"></textarea>
              <input type="text" name="honeypot" style="display:none">
              <input type="hidden" name="accessKey" value="aaaaaaaa-bbbb-cccc-dddd-eeee6666kkkk">
              <input type="hidden" name="subject" value="Contact us from - example.com" />
              <input type="hidden" name="replyTo" value="@">
              <input type="hidden" name="redirectTo" value="https://example.com/contact/success">
              <input class="bg-white cursor-pointer mt-11 w-[60%] p-1 rounded-full font-semibold" type="submit" value="Submit" />
              <img class="submitimg w-6 relative -top-7 right-14 mr-2" src="../assets/images/arrowright.png">
            </form>
          </div>
        </div>
      </header>
      
      <main class="h-full w-full bg-black">
        <video class="mx-auto pt-10 w-[90%] codingvideo" autoplay muted loop playsinline title="Video of WebHive coding a basic website.">
          <source src="../assets/videos/main.mp4">
        </video>
        
        <section id="scrolltocourses" class="bg-black pb-4 text-center grid place-items-center mt-10 mb-10">
          <div class="max-w-[1500px] w-full grid grid-cols-1 lg:grid-cols-2 xl:grid-cols-3 gap-4 p-10" id="courses-container">
            <div class="h-[350px] max-w-[600px] lg:max-w-none mx-auto rounded bg-[#7F7CAF]">
              
              <img class="w-28 mt-4 mr-2 float-right" src="../assets/images/htmlicon.png" alt="">
              
              <h2 class="text-left text-white font-[lemon] text-3xl ml-8 mt-6">Html Course</h2>
              
              <p class="text-left text-white font-bold ml-8 mt-1">10 lessons | 3 projects</p>
              <p class="text-left text-white w-[60%] mt-6 ml-8 text-base">Learn the fundamentals of the programming language HTML. We start from the very bottom and cover everything.</p>
              
              <button @click="save = !save" class="text-[#ffffffb1] flex float-left mt-24 ml-8 "><span class="savetext">Save</span>
                <img v-if="save" class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/saved.png" alt="image of an x">
                <img v-else class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/notsaved.png" alt="image of an x">
              </button>
              
              <div class="buttoncontainer float-right mr-10 mt-20 flex flex-row">
                <button class="px-4 py-2 bg-[#333333] text-white flex items-center justify-center rounded">Learn more</button>
                <button class="px-4 py-2 bg-[#333333] text-white flex items-center justify-center rounded ml-2">Add to basket</button>
              </div>
            </div>
            
            <div class="h-[350px] max-w-[600px] lg:max-w-none mx-auto rounded bg-[#36151E]">
              <img class="w-28 mt-4 mr-4 float-right" src="../assets/images/cssicon.png" alt="">
              
              <h2 class="text-left text-white font-[lemon] text-3xl ml-8 mt-6">CSS Course</h2>
              
              <p class="text-left text-white font-bold ml-8 mt-1">10 lessons | 3 projects</p>
              <p class="text-left text-white w-[60%] mt-6 ml-8 text-base">Learn the fundamentals of the programming language CSS. We start from the very bottom and cover everything.</p>
              
              <button @click="save2 = !save2" class=" text-[#ffffffb1] flex float-left mt-24 ml-8 "><span class="savetext">Save</span>
                <img v-if="save2" class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/saved.png" alt="image of an x">
                <img v-else class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/notsaved.png" alt="image of an x">
              </button>
              
              <div class="buttoncontainer float-right mr-10 mt-20 flex flex-row">
                <button class="px-4 py-2 bg-[#bababa] text-black flex items-center justify-center rounded">Learn more</button>
                <button class="px-4 py-2 bg-[#bababa] text-black flex items-center justify-center rounded ml-2">Add to basket</button>
              </div>
            </div>
            
            <div class="h-[350px] max-w-[600px] lg:max-w-none mx-auto rounded bg-[#113537]">
              <img class="w-32 mt-4 float-right" src="../assets/images/htmlicon.png" alt="">
              
              <h2 class="text-left text-white font-[lemon] text-3xl ml-8 mt-6">JavaScript Course</h2>
              
              <p class="text-left text-white font-bold ml-8 mt-1">10 lessons | 3 projects</p>
              <p class="text-left text-white w-[60%] mt-6 ml-8 text-base">Learn the fundamentals of the programming language JavaScript. We start from the very bottom and cover everything.</p>
              
              <button @click="save3 = !save3" class=" text-[#ffffffb1] flex float-left mt-24 ml-8 "><span class="savetext">Save</span>
                <img v-if="save3" class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/saved.png" alt="image of an x">
                <img v-else class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/notsaved.png" alt="image of an x">
              </button>
              
              <div class="buttoncontainer float-right mr-10 mt-20 flex flex-row">
                <button class="px-4 py-2 bg-[#bababa] text-black flex items-center justify-center rounded">Learn more</button>
                <button class="px-4 py-2 bg-[#bababa] text-black flex items-center justify-center rounded ml-2">Add to basket</button>
              </div>
            </div>
            
            <div class="h-[350px] max-w-[600px] lg:max-w-none mx-auto rounded bg-[#A4B494]">
              <img class="w-32 mt-4 float-right" src="../assets/images/htmlicon.png" alt="">
              
              <h2 class="text-left text-white font-[lemon] text-3xl ml-8 mt-6">Tailwind Course</h2>
              
              <p class="text-left text-white font-bold ml-8 mt-1">10 lessons | 3 projects</p>
              <p class="text-left text-white w-[60%] mt-6 ml-8 text-base">Learn the fundamentals of the programming language Tailwind. We start from the very bottom and cover everything.</p>
              
              <button @click="save4 = !save4" class=" text-[#ffffffb1] flex float-left mt-24 ml-8 "><span class="savetext">Save</span>
                <img v-if="save4" class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/saved.png" alt="image of an x">
                <img v-else class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/notsaved.png" alt="image of an x">
              </button>
              
              <div class="buttoncontainer float-right mr-10 mt-20 flex flex-row">
                <button class="px-4 py-2 bg-[#333333] text-white flex items-center justify-center rounded">Learn more</button>
                <button class="px-4 py-2 bg-[#333333] text-white flex items-center justify-center rounded ml-2">Add to basket</button>
              </div>
            </div>
            
            <div class="h-[350px] max-w-[600px] lg:max-w-none mx-auto rounded bg-[#202030]">
              <img class="w-32 mt-4 float-right" src="../assets/images/htmlicon.png" alt="">
              
              <h2 class="text-left text-white font-[lemon] text-3xl ml-8 mt-6">Vue Course</h2>
              
              <p class="text-left text-white font-bold ml-8 mt-1">10 lessons | 3 projects</p>
              <p class="text-left text-white w-[60%] mt-6 ml-8 text-base">Learn the fundamentals of the programming language Vue. We start from the very bottom and cover everything.</p>
              
              <button @click="save5 = !save5" class=" text-[#ffffffb1] flex float-left mt-24 ml-8 "><span class="savetext">Save</span>
                <img v-if="save5" class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/saved.png" alt="image of an x">
                <img v-else class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/notsaved.png" alt="image of an x">
              </button>
              
              <div class="buttoncontainer float-right mr-10 mt-20 flex flex-row">
                <button class="px-4 py-2 bg-[#bababa] text-black flex items-center justify-center rounded">Learn more</button>
                <button class="px-4 py-2 bg-[#bababa] text-black flex items-center justify-center rounded ml-2">Add to basket</button>
              </div>
            </div>
            
            <div class="h-[350px] max-w-[600px] lg:max-w-none mx-auto rounded bg-[#AE9273]">
              <img class="w-32 mt-4 float-right" src="../assets/images/htmlicon.png" alt="">
              
              <h2 class="text-left text-white font-[lemon] text-3xl ml-8 mt-6">Design Course</h2>
              
              <p class="text-left text-white font-bold ml-8 mt-1">10 lessons | 3 projects</p>
              <p class="text-left text-white w-[60%] mt-6 ml-8 text-base">Learn the fundamentals of the programming language Design. We start from the very bottom and cover everything.</p>
              
              <button @click="save6 = !save6" class=" text-[#ffffffb1] flex float-left mt-24 ml-8 "><span class="savetext">Save</span>
                <img v-if="save6" class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/saved.png" alt="image of an x">
                <img v-else class="saveicon w-4 opacity-60 mt-[5px] ml-1" src="../assets/images/notsaved.png" alt="image of an x">
              </button>
              
              <div class="buttoncontainer float-right mr-10 mt-20 flex flex-row">
                <button class="px-4 py-2 bg-[#333333] text-white flex items-center justify-center rounded">Learn more</button>
                <button class="px-4 py-2 bg-[#333333] text-white flex items-center justify-center rounded ml-2">Add to basket</button>
              </div>
            </div>
          </div>
        </section>
        
        <section class="progresssection p-20">
          <div class="bg-[#111111df] pb-10 w-[70%] mx-auto rounded-2xl">
            <h2 class="text-white text-center font-bold text-[50px] p-20">We Believe In Progress</h2>
            
            <div class="grid place-items-center grid-rows-1 grid-cols-3 gap-6 mx-auto w-[90%]">
              <div class="w-[300px] h-[300px] bg-[#ffffffdf] shadow-2xl rounded-lg border-2 border-black"></div>
              <div class="w-[300px] h-[300px] bg-[#ffffffdf] shadow-2xl rounded-lg border-2 border-black"></div>
              <div class="w-[300px] h-[300px] bg-[#ffffffdf] shadow-2xl rounded-lg border-2 border-black"></div>
            </div>
          </div>
        </section>
        
        
        <section id="rotate-content" class="w-full overflow-hidden h-[1100px] bg-[#111111]">
          <div id="image-section" class="w-[1000px] mt-22 h-[1100px] relative left-1/2 transform scale-75 sm:scale-100 -translate-x-1/2 grid grid-cols-4 place-items-center">
            <img class="first-column border-2 w-[200px] rounded-xl transform rotate-[-15deg] mt-60" src="../assets/images/htmlpage.png">
            <img class="second-column border-2 w-[200px] rounded-xl transform rotate-[-15deg] mr-11 mb-32" src="../assets/images/csspage.png">
            <img class="third-column border-2 w-[200px] rounded-xl transform rotate-[-15deg] mb-32" src="../assets/images/jspage.png">
            <img class="fourth-column border-2 w-[200px] rounded-xl transform rotate-[-15deg]" src="../assets/images/designpage.png">
            
            <h2 id="middle-title" class="text-white font-bold text-4xl mb-8 absolute ml-20">Create <span class="text-purple-500">real</span> content <br> learning from the <span class="text-purple-500">best</span></h2>
            
            <img class="first-column border-2 w-[200px] rounded-xl transform -rotate-[15deg] mb-20 ml-28" src="../assets/images/packagepage.png">
            <img class="second-column border-2 w-[200px] rounded-xl transform -rotate-[15deg] mt-8 ml-40" src="../assets/images/vuepage.png">
            <img class="third-column border-2 w-[200px] rounded-xl transform -rotate-[15deg] mt-8 ml-40" src="../assets/images/tailwindpage.png">
            <img class="fourth-column border-2 w-[190px] object-cover h-[250px] rounded-xl transform -rotate-[15deg] mb-52 ml-40" src="../assets/images/mainpage.png">
          </div>
        </section>
        
        <!-- <section class="w-full h-[600px] bg-[#111111] flex justify-left items-center">
          <img class="h-full" src="../static/images/iphone.png">
          <img class="h-full" src="../static/images/ipadwebsite.png">
        </section> -->
        
        <section class="reviewsection bg-no-repeat bg-center bg-cover w-full bg-[#111111]">
          <div id="expand-words" class="overflow-x-hidden circle-container text-white font-bold">
            <div class="mt-20 ml-4 flex flex-row z-10">
              <p class="text-3xl absolute -mt-10 ml-4">
                <span id="slidenumber">{{ currentIndex + 1 }}</span> /
                <span id="slidestotal">{{ reviewcards.length }}</span>
              </p>
              <div v-for="(card, index) in reviewcards" :key="index" class="reviewcards rounded-lg bg-[#44444430] shadow-lg duration-200 w-[550px]" :class="{ 'opacity-1': index === currentIndex, 'opacity-50': index !== currentIndex }" :style="{ 'margin': '4px' }">
                <div class="p-8">
                  <h2 class="text-3xl">{{ card.name }}</h2>
                  <p class="font-normal w-[400px] mt-4 text-md">{{ card.content }}</p>
                  <div class="flex items -ml-2 w-[50px] mt-4">
                    <img v-for="star in card.stars" :key="star" src="../assets/images/star-yellow.png">
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="ml-4 mt-2">
            <button @click="backbutton" class="w-12 h-12 text-white rounded-full m-1 active:border">
              <img class="w-6 ml-3" src="../assets/images/arrowleft.png">
            </button>
            <button @click="forwardbutton" class="w-12 h-12 text-white rounded-full m-1 active:border">
              <img class="w-6 ml-3" src="../assets/images/arrowright.png">
            </button>
          </div>
        </section>
      </main>
    </div>
  </template>
  
  <style lang="postcss">
    @import url('https://fonts.googleapis.com/css2?family=Lemon&display=swap');
    
    :root {
      scroll-behavior: smooth;
    }
    
    .icon {
      font-family: 'Lemon';
    }
    
    #image-section img {
      box-shadow: 0 0 40px rgb(0, 0, 0);
    }
    
    ::-webkit-scrollbar {
      @apply w-[10px];
    }
    
    ::-webkit-scrollbar-track {
      @apply bg-[#232323];
    }
    
    ::-webkit-scrollbar-thumb {
      @apply rounded-[25px] bg-[#4c4c4c];
    }
    
    .formsection input[type="submit"]:hover .submitimg {
      @apply left-[100px];
    }
    
    #rotate-content {
      background-image: url('../assets/images/blueblur.png');
      background-repeat: no-repeat;
      background-position: center;
    }
    
    .reviewcards p {
      @apply font-[15px];
    }
    
    .htmltagdiv p {
      @apply inline-block mr-[10px];
    }
    
    .textboxes {
      box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
    }
    
    .ActiveScrollNav {
      @apply bg-black h-[50px] text-[15px];
    }
    .NotActiveScrollNav {
      @apply bg-[#0d0d0dcf] h-auto text-[16px];
    }
    
    .ActiveScrollIcon {
      @apply text-[15px];
    }
    .NotActiveScrollIcon {
      @apply text-[18px];
    }
    
    .ActiveScrollCodedin {
      @apply -mt-10;
    }
    .NotActiveScrollCodedin {
      @apply mt-0;
    }
    
    .progresssection {
      background-image: url("https://images.pexels.com/photos/1437953/pexels-photo-1437953.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1");
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;
    }
    
    #nav-icon3 {
      -webkit-transform: rotate(0deg);
      -moz-transform: rotate(0deg);
      -o-transform: rotate(0deg);
      transform: rotate(0deg);
      -webkit-transition: .5s ease-in-out;
      -moz-transition: .5s ease-in-out;
      -o-transition: .5s ease-in-out;
      transition: .5s ease-in-out;
      @apply w-[60px] h-[45px] absolute right-[-20px] top-[10px] cursor-pointer;
    }
    #nav-icon3 span {
      -webkit-transform: rotate(0deg);
      -moz-transform: rotate(0deg);
      -o-transform: rotate(0deg);
      transform: rotate(0deg);
      -webkit-transition: .25s ease-in-out;
      -moz-transition: .25s ease-in-out;
      -o-transition: .25s ease-in-out;
      transition: .25s ease-in-out;
      @apply block absolute h-[3px] w-[25px] bg-white rounded-[9px] opacity-100 left-0;
    }
    #nav-icon3 span:nth-child(1) {
      @apply top-0;
    }
    #nav-icon3 span:nth-child(2),#nav-icon3 span:nth-child(3) {
      @apply top-2;
    }
    #nav-icon3 span:nth-child(4) {
      @apply top-4;
    }
    #nav-icon3.open span:nth-child(1) {
      @apply top-0 w-0 left-[50%];
    }
    #nav-icon3.open span:nth-child(2) {
      -webkit-transform: rotate(45deg);
      -moz-transform: rotate(45deg);
      -o-transform: rotate(45deg);
      transform: rotate(45deg);
    }
    #nav-icon3.open span:nth-child(3) {
      -webkit-transform: rotate(-45deg);
      -moz-transform: rotate(-45deg);
      -o-transform: rotate(-45deg);
      transform: rotate(-45deg);
    }
    #nav-icon3.open span:nth-child(4) {
      @apply top-[18px] w-0 left-[50%];
    }
  </style>