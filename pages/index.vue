<template>
  <div id="app">
    <header class="h-[550px] w-full">
      <video autoplay muted playsinline loop class="w-full object-cover h-full">
        <source src="../static/videos/1two.mp4" type="video/mp4">
      </video>
      
      <div class="absolute left-7 top-[300px] sm:top-[350px] text-white pb-14 sm:w-[500px] w-[300px] max-w-md p-4 rounded-lg duration-200">
        <h1 class="text-4xl  font-semibold">Learn to code websites</h1>
        <p class="opacity-60 italic text-[13px] mt-1">Learn how to make websites through coding HTML, CSS, and JavaScript. Additionally, master your design skills.</p>
        <button class="bg-[#658ed5] text-black pr-2 pl-2 p-[3px] text-[13.5px] absolute bottom-5 rounded font-semibold">See more</button>
      </div>
      
      <nav class="sm:h-[50px] h-[40px] fixed left-2 w-[110px] sm:w-[130px] rounded-[20px] bg-[#222222bc] top-3 z-10">
        <a href="" id="icon" class="labelsclass left-5 sm:text-lg text-sm text-white absolute top-2.5 cursor-pointer">WebHive</a>
      </nav>
      
      <nav class="h-[40px] sm:h-[50px] fixed right-2 sm:w-[90%] w-[300px] text-xs sm:text-base max-w-[450px] rounded-[20px] bg-[#222222bc] top-3 z-10">
        <div class="labelsclass text-white font-semibold w-[450px] h-full absolute left-4 top-[11px]">
          <a class="sm:mx-2 mr-1 cursor-pointer">Home</a>
          <a class="sm:mx-2 mx-1 cursor-pointer">Courses</a>
          <a class="sm:mx-2 mx-1 cursor-pointer">Course info</a>
          <a class="sm:mx-2 mx-1 cursor-pointer">About</a>
          <a class="sm:mx-2 ml-1 cursor-pointer contactbutton">Contact</a>
        </div>
        
        <a class="labelsclass absolute right-5 w-6 cursor-pointer top-2.5 rounded-3xl hidden sm:block">
          <img src="../static/images/basket-white.png">
        </a>
      </nav>
      
      <div class="contactsection pointer-events-none opacity-0 rounded-2xl bg-[#000000f2] w-[400px] h-[450px] fixed right-6 z-10 top-20 grid-cols-2 place-content-center">
        <div class="w-[130px] h-full left-0 absolute bg-[#222222c0] rounded-l-xl contactbuttonsection">
          <h2 class="text-white text-2xl font-semibold ml-6 mt-4">Find us</h2>
          
          <div class="grid grid-rows-5 grid-cols-1 place-items-center gap-2 mt-6 w-full">
            <div class="h-16 rounded-full w-[64px] bg-[#222222] childdiv hover:cursor-pointer">
              <img class="mix-blend-lighten w-10 ml-3 mt-3" src="../static/images/facebook.png">
            </div>
            <div class="h-16 rounded-full w-[64px] bg-[#222222] childdiv hover:cursor-pointer">
              <img class="mix-blend-lighten w-10 ml-3 mt-3" src="../static/images/tiktokwhite.png">
            </div>
            <div class="h-16 rounded-full w-[64px] bg-[#222222] childdiv hover:cursor-pointer">
              <img class="mix-blend-lighten w-10 ml-3 mt-3" src="../static/images/insta.png">
            </div>
            <div class="h-16 rounded-full w-[64px] bg-[#222222] childdiv hover:cursor-pointer">
              <img class="mix-blend-lighten w-10 ml-3 mt-3" src="../static/images/git.png">
            </div>
            <div class="h-16 rounded-full w-[64px] bg-[#222222] childdiv hover:cursor-pointer">
              <img class="mix-blend-lighten w-10 ml-3 mt-3" src="../static/images/twi.png">
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
            <input class="bg-[#222222] cursor-pointer mt-11 w-[60%] p-1 rounded-full font-semibold" type="submit" value="Submit" />
            <img class="submitimg w-6 relative -top-7 right-14 mr-2" src="../static/images/arrowright.png">
          </form>
        </div>
      </div>
    </header>
    
    <main class="h-full w-full bg-black">
      <section class="bg-black pb-4 text-center grid place-items-center">
        <div class="max-w-[1600px] w-full transform scale-90 lg:scale-100 -mt-24 sm:-mt-12 lg:mt-2" id="courses-container">
          <div class="text-left inline-block ml-4 mt-5 w-[450px] h-[300px] rounded-md bg-[#111111] text-white pt-3">
            <img src="../static/images/html.png" class="h-[100px] w-[230px] object-cover ml-[12px] rounded-md">
            
            <div class="w-[140px] h-[80px] float-right mr-8 -mt-24 font-semibold">
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">See more</button>
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">Add To Basket</button>
            </div>
            
            <div class="ml-[13px] mt-4">
              <h2 class="text-xl font-bold">HTML</h2>
              <p class="text-[13px] opacity-60 mt-[5px] leading-4">Learn to code HTML. Starting from the ground up, teaching HTML/HTML5 through coding challenges and creative exercises.</p>
              
              <ul class="list-disc ml-4 mt-4">
                <li class="-mt-2">Syntax And Structure</li>
                <li class="-mt-2">Elements and Attributes</li>
                <li class="-mt-2">Formatting</li>
                <li class="-mt-2">Multimedia</li>
                <li class="-mt-2">Basic CSS</li>
              </ul>
            </div>
          </div>
          
          <div class="text-left inline-block  ml-4 mt-5 w-[450px] h-[300px] rounded-md bg-[#111111] text-white pt-3">
            <img src="../static/images/css.png" class="h-[100px] w-[230px] object-cover ml-[12px] rounded-md">
            
            <div class="w-[140px] h-[80px] float-right mr-8 -mt-24 font-semibold">
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">See more</button>
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">Add To Basket</button>
            </div>
            
            <div class="ml-[13px] mt-4">
              <h2 class="text-xl font-bold">HTML</h2>
              <p class="text-[13px] opacity-60 mt-[5px] leading-4">Learn to code HTML. Starting from the ground up, teaching HTML/HTML5 through coding challenges and creative exercises.</p>
              
              <ul class="list-disc ml-4 mt-4">
                <li class="-mt-2">Syntax And Structure</li>
                <li class="-mt-2">Elements and Attributes</li>
                <li class="-mt-2">Formatting</li>
                <li class="-mt-2">Multimedia</li>
                <li class="-mt-2">Basic CSS</li>
              </ul>
            </div>
          </div>
          
          <div class="text-left inline-block ml-4  mt-5 w-[450px] h-[300px] rounded-md bg-[#111111] text-white pt-3">
            <img src="../static/images/js.png" class="h-[100px] w-[230px] object-cover ml-[12px] rounded-md">
            
            <div class="w-[140px] h-[80px] float-right mr-8 -mt-24 font-semibold">
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">See more</button>
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">Add To Basket</button>
            </div>
            
            <div class="ml-[13px] mt-4">
              <h2 class="text-xl font-bold">HTML</h2>
              <p class="text-[13px] opacity-60 mt-[5px] leading-4">Learn to code HTML. Starting from the ground up, teaching HTML/HTML5 through coding challenges and creative exercises.</p>
              
              <ul class="list-disc ml-4 mt-4">
                <li class="-mt-2">Syntax And Structure</li>
                <li class="-mt-2">Elements and Attributes</li>
                <li class="-mt-2">Formatting</li>
                <li class="-mt-2">Multimedia</li>
                <li class="-mt-2">Basic CSS</li>
              </ul>
            </div>
          </div>
          
          <div class="text-left inline-block ml-4 mt-5  w-[450px] h-[300px] rounded-md bg-[#111111] text-white pt-3">
            <img src="../static/images/design.png" class="h-[100px] w-[230px] object-cover ml-[12px] rounded-md">
            
            <div class="w-[140px] h-[80px] float-right mr-8 -mt-24 font-semibold">
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">See more</button>
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">Add To Basket</button>
            </div>
            
            <div class="ml-[13px] mt-4">
              <h2 class="text-xl font-bold">HTML</h2>
              <p class="text-[13px] opacity-60 mt-[5px] leading-4">Learn to code HTML. Starting from the ground up, teaching HTML/HTML5 through coding challenges and creative exercises.</p>
              
              <ul class="list-disc ml-4 mt-4">
                <li class="-mt-2">Syntax And Structure</li>
                <li class="-mt-2">Elements and Attributes</li>
                <li class="-mt-2">Formatting</li>
                <li class="-mt-2">Multimedia</li>
                <li class="-mt-2">Basic CSS</li>
              </ul>
            </div>
          </div>
          
          <div class="text-left inline-block ml-4 mt-5  w-[450px] h-[300px] rounded-md bg-[#111111] text-white pt-3">
            <img src="../static/images/package.png" class="h-[100px] w-[230px] object-cover ml-[12px] rounded-md">
            
            <div class="w-[140px] h-[80px] float-right mr-8 -mt-24 font-semibold">
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">See more</button>
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">Add To Basket</button>
            </div>
            
            <div class="ml-[13px] mt-4">
              <h2 class="text-xl font-bold">HTML</h2>
              <p class="text-[13px] opacity-60 mt-[5px] leading-4">Learn to code HTML. Starting from the ground up, teaching HTML/HTML5 through coding challenges and creative exercises.</p>
              
              <ul class="list-disc ml-4 mt-4">
                <li class="-mt-2">Syntax And Structure</li>
                <li class="-mt-2">Elements and Attributes</li>
                <li class="-mt-2">Formatting</li>
                <li class="-mt-2">Multimedia</li>
                <li class="-mt-2">Basic CSS</li>
              </ul>
            </div>
          </div>
          
          <div class="text-left inline-block ml-4 mt-5  w-[450px] h-[300px] rounded-md bg-[#111111] text-white pt-3">
            <img src="../static/images/vue.png" class="h-[100px] w-[230px] object-cover ml-[12px] rounded-md">
            
            <div class="w-[140px] h-[80px] float-right mr-8 -mt-24 font-semibold">
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">See more</button>
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">Add To Basket</button>
            </div>
            
            <div class="ml-[13px] mt-4">
              <h2 class="text-xl font-bold">HTML</h2>
              <p class="text-[13px] opacity-60 mt-[5px] leading-4">Learn to code HTML. Starting from the ground up, teaching HTML/HTML5 through coding challenges and creative exercises.</p>
              
              <ul class="list-disc ml-4 mt-4">
                <li class="-mt-2">Syntax And Structure</li>
                <li class="-mt-2">Elements and Attributes</li>
                <li class="-mt-2">Formatting</li>
                <li class="-mt-2">Multimedia</li>
                <li class="-mt-2">Basic CSS</li>
              </ul>
            </div>
          </div>
          
          <div class="text-left inline-block ml-4 mt-5  w-[450px] h-[300px] rounded-md bg-[#111111] text-white pt-3">
            <img src="../static/images/tailwind.png" class="h-[100px] w-[230px] object-cover ml-[12px] rounded-md">
            
            <div class="w-[140px] h-[80px] float-right mr-8 -mt-24 font-semibold">
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">See more</button>
              <button class="bg-[#222222] w-full h-1/2 m-1 rounded pl-2 pr-2 duration-200 hover:bg-black">Add To Basket</button>
            </div>
            
            <div class="ml-[13px] mt-4">
              <h2 class="text-xl font-bold">HTML</h2>
              <p class="text-[13px] opacity-60 mt-[5px] leading-4">Learn to code HTML. Starting from the ground up, teaching HTML/HTML5 through coding challenges and creative exercises.</p>
              
              <ul class="list-disc ml-4 mt-4">
                <li class="-mt-2">Syntax And Structure</li>
                <li class="-mt-2">Elements and Attributes</li>
                <li class="-mt-2">Formatting</li>
                <li class="-mt-2">Multimedia</li>
                <li class="-mt-2">Basic CSS</li>
              </ul>
            </div>
          </div>
        </div>
      </section>
      
      <section id="rotate-content" class="w-full overflow-hidden h-[1100px] bg-[#111111]">
        <div id="image-section" class="w-[1000px] mt-22 h-[1100px] relative left-1/2 transform scale-75 sm:scale-100 -translate-x-1/2 grid grid-cols-4 place-items-center">
          <img class="first-column border-2 w-[200px] rounded-xl transform rotate-[-15deg] mt-60" src="../static/images/htmlpage.png">
          <img class="second-column border-2 w-[200px] rounded-xl transform rotate-[-15deg] mr-11 mb-32" src="../static/images/csspage.png">
          <img class="third-column border-2 w-[200px] rounded-xl transform rotate-[-15deg] mb-32" src="../static/images/jspage.png">
          <img class="fourth-column border-2 w-[200px] rounded-xl transform rotate-[-15deg]" src="../static/images/designpage.png">
          <h2 id="middle-title" class="text-white font-bold text-4xl mb-8 absolute ml-20">Create <span class="text-purple-500">real</span> content <br> learning from the <span class="text-purple-500">best</span></h2>
          <img class="first-column border-2 w-[200px] rounded-xl transform -rotate-[15deg] mb-20 ml-28" src="../static/images/packagepage.png">
          <img class="second-column border-2 w-[200px] rounded-xl transform -rotate-[15deg] mt-8 ml-40" src="../static/images/vuepage.png">
          <img class="third-column border-2 w-[200px] rounded-xl transform -rotate-[15deg] mt-8 ml-40" src="../static/images/tailwindpage.png">
          <img class="fourth-column border-2 w-[190px] object-cover h-[250px] rounded-xl transform -rotate-[15deg] mb-52 ml-40" src="../static/images/mainpage.png">
        </div>
      </section>
      
      <section class="w-full h-[600px] bg-[#111111] flex justify-left items-center">
        <img class="h-full" src="../static/images/iphone.png">
        <img class="h-full" src="../static/images/ipadwebsite.png">
      </section>
      
      <section class="reviewsection h-[600px] w-full bg-[#111111]">
        <div id="expand-words" class="overflow-x-hidden h-[500px] circle-container text-white font-bold">
          <div class="w-[5000px] mt-20 flex flex-row z-10">
            <p class="text-3xl absolute -mt-10 ml-4">
              <span id="slidenumber">{{ currentIndex + 1 }}</span>
              <span id="slidestotal">{{ reviewcards.length }}</span>
            </p>
            <div v-for="(card, index) in reviewcards" :key="index" class="reviewcards rounded-xl bg-[#000000bc] duration-200 w-[600px]" :class="{ 'opacity-1': index === currentIndex, 'opacity-50': index !== currentIndex }" :style="{ 'margin': '4px', 'height': '350px' }">
              <div class="p-8">
                <h2 class="text-3xl">{{ card.name }}</h2>
                <p class="font-normal w-[400px] mt-4">{{ card.content }}</p>
                <div class="flex items -ml-2 w-[50px] mt-4">
                  <img v-for="star in card.stars" :key="star" src="../static/images/star-yellow.png">
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="ml-4 -mt-6">
          <button @click="backbutton" class="w-12 h-12 bg-[#000000bc] text-white rounded-full m-1 active:border">
            <img class="w-6 ml-3" src="../static/images/arrowleft.png">
          </button>
          <button @click="forwardbutton" class="w-12 h-12 bg-[#000000bc] text-white rounded-full m-1 active:border">
            <img class="w-6 ml-3" src="../static/images/arrowright.png">
          </button>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
export default {
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
        name: "Antoine Leth",
        content: "Bought the package course not really knowing what i expect but i was pleasantly surprised...",
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
      ]
    };
  },
  methods: {
    forwardbutton() {
      if (this.currentIndex < this.reviewcards.length - 1) {
        this.currentIndex++;
      }
    },
    backbutton() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      }
    },
    isElementInViewport(element) {
      const rect = element.getBoundingClientRect();
      return (
      rect.top >= 0 &&
      rect.left >= 0 &&
      rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &&
      rect.right <= (window.innerWidth || document.documentElement.clientWidth)
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
    }
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
    
    window.addEventListener('scroll', () => {
      var nav = document.querySelectorAll('nav');
      
      if (window.scrollY < 30) {
        for (var i = 0; i < nav.length; i++) {
          nav[i].style.transition = '0.2s ease-in-out';
          nav[i].style.backgroundColor = '#222222bc';
        }
      } else {
        for (var i = 0; i < nav.length; i++) {
          nav[i].style.transition = '0.2s ease-in-out';
          nav[i].style.backgroundColor = '#333333';
        }
      }
    });
    
    document.querySelector('.contactbutton').addEventListener('click', () => {
      document.querySelector('.contactsection').style.transition = '0.2s ease-in-out';
      document.querySelector('.contactsection').style.pointerEvents = 'all';
      document.querySelector('.contactsection').style.opacity = '1';
    });
    
    document.querySelector('main').addEventListener('click', () => {
      document.querySelector('.contactsection').style.transition = '0.2s ease-in-out';
      document.querySelector('.contactsection').style.opacity = '0';
      document.querySelector('.contactsection').style.pointerEvents = 'none';
    });
    
    document.querySelector('.formsection input[type="submit"]').addEventListener('mouseover', () => {
      document.querySelector('.submitimg').style.transition = '300ms ease-in-out';
      document.querySelector('.submitimg').style.left = '63px';
    });
    document.querySelector('.submitimg').addEventListener('mouseover', () => {
      document.querySelector('.submitimg').style.transition = '300ms ease-in-out';
      document.querySelector('.submitimg').style.left = '63px';
    });
    
    document.querySelector('.formsection input[type="submit"]').addEventListener('mouseout', () => {
      document.querySelector('.submitimg').style.transition = '200ms ease-in-out';
      document.querySelector('.submitimg').style.left = '-55px';
    });
  }
}
</script>

<style scoped>
#icon {
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

.reviewsection {
  background-image: url('../static/images/blueblur.png');
  @apply bg-no-repeat bg-center bg-cover;
}

.reviewcards p {
  @apply font-[15px];
}

.htmltagdiv p {
  @apply inline-block mr-[10px];
}
</style>