<template>
    <div class="messages">

        <!-- Header -->
        <el-row>
            <el-col :xs="2" :sm="2" :md="2" :lg="2" :xl="2">
                <el-button @click="goBack()" class="back_button" type="danger" circle
                           icon="el-icon-d-arrow-left"></el-button>
            </el-col>
            <el-col :xs="24" :sm="24" :md="24" :lg="24" :xl="24">
                <h1 style="margin-left: 50px">Messages</h1>
            </el-col>
        </el-row>

        <!-- Content -->
        <el-row type="flex" justify="center">
            <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
                <div class="block" style="overflow:auto; min-height: 70vh">

                    <loading :active="loaderLoading"
                             :is-full-page="loaderFullPage"
                             :color="loaderColor"
                             :opacity="loaderOpacity"
                             :height="loaderHeight"
                             :width="loaderWidth"
                             :loader="loaderStyle"></loading>

                    <transition name="el-zoom-in-bottom">
                        <el-timeline class="messages_timeline"
                                     v-show="showTimeline">

                            <el-timeline-item timestamp="And....that's how I met you 😜 " placement="top">
                                <el-card>
                                    <el-image :src="img1" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>Haha I am starting these messages with this goofy pic😂 
                                        Yaar this photo of us will always have a special place in my heart. Tujhe yaad hai mai toh bohot nervous 
                                        tha uss time pe while driving cause my Crush was sitting behind meeee!!! I don't know tujhe wo kaise samjha ki I am nervous and you started 
                                        talking to me and aaj tera kitna bhi awaaj sunu mujhe kam hi lagta tha 😊 Sexyy Accent you've got :D. Thank you so much for coming to Mehak's Party that dayy. I know you were not going to come initially but I am so glad you did 😘. Last year was the best year of my life & all credit goes to you  </h3>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Gathering Diaries..." placement="top">
                                <el-card>
                                    <el-image :src="img2" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>Oof just look at you 🥵🥵 Slaying out there as usual. I remember seeing you that day but too afraid to speak to you cause we didn't know each other na tab.
                                        Uss din na I really wanted to say that "You are looking gorgeous". But himmat hi nhi hui 😗. Koi na I will say it abhi: "YOU ARE GORGEOUS!!"
                                        That night my roommates were stalking you only. Well I won't blame them for doing that cause just look at youuuu </h3>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Best Birthday of My Life" placement="top">
                                <el-card>
                                    <el-image :src="img3" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item placement="top">
                                <el-card>
                                    <h3>I am sure no upcoming birthdays will ever surpass this one kyuki you were
                                        a part of this one 🤗. Once again I am sorry I spoiled your surprise that night 😗. 
                                        I may never have told you this but I remember how you came
                                        to Pune that morning only, just for my Birthday, and that made me feel so special yaar😭. Your friends
                                        were upset kyuki tu banglore se jaldi jaa rahi thi but yet you came for me.
                                        That day I realised that I am dating an Angel only. Thank You Sooo Much Shrutii😭
                                        Hahaha I love this pic, see how awkwardly you are smiling here 🙂 Lol. Best Birthday ever!   
                                    </h3>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Sorriii Shrutiii" placement="top">
                                <el-card>
                                    <el-image :src="img4" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>Tujhe yaad hai ki nai pata nhi but this pic was taken after our first big fight,
                                        caused by a miscommunication from my part🤦‍♂️. You must be thinking ki yaar aise 
                                        happy wale occassion me ye photo kyu daala 🤷‍♂️ but to be honest iss fight ke baad 
                                        I think we came a little more closer than what we were pehle. For me it's a sweet memory that I will 
                                        always cherish in my heart because that fight brought us closer 🤗. That day I decided ki I will try not to hurt you ever again (I may have failed in this part 🤦)
                                    </h3>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Your first photo in my iPhone" placement="top">
                                <el-card>
                                    <el-image :src="img5" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>C'mon yaar how can someone be this Cuteeee ahhhhhhhh. Uss din you came from office to Viman Nagar
                                        and we went to a new place in khau galli. I was rambling on & on about my iPhone and there you were just
                                        listening to my nonsense talk with a pretty shine in your eyes. I could tell how happy you were just to see me happy😭.
                                        Itna accha koi kaise ho sakta hai yaar. I wanted to kiss you hard uss time but fir jaise taise maine control kiya
                                        khud ko 😶‍🌫️. You even bought me a BR icecream that day😁 Ooof so many parties you have given me. The Only 
                                        one who was cuter than my iPhone that day was YOUUUUUU 💕
                                    </h3>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Hey Siri! 'Play We Never Go Out of Style' by T.Swift" placement="top">
                                <el-card>
                                    <el-image :src="img6" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>Yaar ye apne best photos me se ek hai 😍. 
                                        We were just waiting for baarish to stop and timepass karte karte you clicked this beaut photo :D
                                        Iss photo ko dekhne ke baad hi log mujhe Colgate boy bulate hai, All Thanks to You Cutie 💕.
                                        We went to Grandmama's Cafe that day to celebrate your NEU ka admit. It was so fun yaar. Do you remember
                                        waha ka waiter hume kaise looks dera tha 😂. Creepy af. Iss din maine party diya tha tujhe haha😉
                                    </h3>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Temple trip" placement="top">
                                <el-card>
                                    <el-image :src="img7" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        Bhai sahab this morning ko when I came to pick you up for mandir & jab tu gate se bahar aayi,
                                        my jaw dropped literally after seeing you in this Kurti and those beaut earrings. I was spellbound.
                                        I never asked you about why you came to mandir with me but it doesn't matter because I was very very happy that you joined
                                        me for mandir. Uss din that Temple & You were just tooo gorgeous for me to handle 🫰🫰 
                                    </h3>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="TAMU Celebrations!!!" placement="top">
                                <el-card>
                                    <el-image :src="img8" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        The Big day was here and we were celebrating your admit into TAMU.
                                        One of the happiest days of both of our lives cause you got into one of the best clgs & mai toh tere liye khush tha.
                                        This was again teri treat (I am losing this Treat Battle now 😭). Idhar ka Mushroom soup was so yum.
                                        I was just looking at you uss din and mujhe kuch aur karna bhi nhi tha uske alawa. I was dil se happy
                                        cause all your hardwork finally paid off😁. You were looking so cute that day too (Ab to aadat si mujhko tu cute dikhne ki)
                                    </h3>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Late mornings...." placement="top">
                                <el-card>
                                    <el-image :src="img9" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        Hushhh this was one of those lazy subah jisme we directly used to do so-called Brunch and have some tasty chai with. Also, keeping an eye on chotu cause he used to stalk you a lot 😶‍🌫️. I think he had a crush on you (just like every other guy jisse tune sirf eye contact kiya hai, cause that's all it takes)
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Bruises and Scarss" placement="top">
                                <el-card>
                                    <el-image :src="img10" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        Yaar I just start laughing zor zor se whenever I remember this incident😂😂.
                                        First of all you were so afraid to even hold the handle of our scooty. Uske baad while driving, you used to scream beech beech me lol.
                                        Fir the best part was the confusion between accelrator and brakes 🤣🤣🤣. Ohh God it was so fun to fall into those bushes (It did hurt though).
                                        Then we went to that random open ground jaha pe this pic was clicked. I wonder why we never visted that place again.
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Banglore Dayss was it ?" placement="top">
                                <el-card>
                                    <el-image :src="img11" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        This photo I stole from your snap hehe. You were at Mehak's place and this is the first time we did a movie party sort of. Why didn't we finish that movie I can't remeber 😭.
                                        Still this is one of my fav memories with you😁. Because of all the disturbances we were facing and yet you were so patient throughout the chaos 🤗 Why are you so cuteee!!???
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Shreya's Birthday" placement="top">
                                <el-card>
                                    <el-image :src="img12" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        Dudeee we got so bored here in this party (Krishna ko mat batana 😶‍🌫️). Still I like this memory of us
                                        kyuki uss time pe I didn't want to dance and was just sitting aur tab you just sat with me to give me company 😭. Thank You So Muchhh for your constant support!
                                        And if I haven't said this enough I am really sorry, but know this ki I always am grateful for your support 🤗  
                                    </h3>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Marine Driveeee" placement="top">
                                <el-card>
                                    <el-image :src="img13" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        Yaar how can I not include this pic. It was the most fun trip I had in ages. You made it the Best trip of my life.
                                        OYO Rajdoot, chinese khana, your first train ka safar, ice cream sandwich, meeting Vedant Siddhant Sahu,
                                        lying down on the Marine, taking selfies & judging people 😂. Wo chaupati ki pav bhaji, paani puri, Ice gola (which you couldn't finish hehe)
                                        And most important, Moving train se utarna and girna😶‍🌫️🤣. Damn yaar it was an adventure itself. I can't remember being this much happy jitna mai iss trip pe tha.
                                        All Thanks to you 🤗 You made it memorable mere liye for a lifetime! I am Not kidding, it was the best 
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Water Cycle 🚲" placement="top">
                                <el-card>
                                    <el-image :src="img14" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>Easily the best night we ever had. My Dumbass being confused between Dominos and Pizza Hut, and in the end making the wrong choice 🤣. You never even complained once that night yaar, you always being so considerate 🥰.
                                        We then had that ghaitya ice cream too (Not a good food day I must say). Uske baad we kept talking for like an hour, making list of my wannabe GF's 😂 (Why do we do this 😭). Then came the kissa of Water-Cycle and man 
                                        you just couldn't stop laughing, Seeing you laugh whole heartedly filled my heart with so much warmth yaar. Smiling and laughing Shruti is my favorite I realised then😁. I hope you always keep laughing and be happy like you were 
                                        that night. I will always try to make you laugh. Seeing you giggle is my favorite thing now.
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Back to Pune from Nagpur" placement="top">
                                <el-card>
                                    <el-image :src="img15" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        I remember this day acche se cause I was insiting on going home at night kyuki Sukrut bhaiyya aaye the Eden pe.
                                        You were so sad and angry that you didn't even talk to me while I was leaving. After 15 mins when I came back to your door,
                                        and saw your face lit up mujhe door pe dekhke, I knew it was the best decision to come back to Amba. I never wanted to hurt you in any way yaar
                                        but unknowingly it happens. You hugged me then. Now I am longing for that tight hug you gave me. We celebrated afterwards with a Waffle🫰 
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Haha...Fav Photo Mera" placement="top">
                                <el-card>
                                    <el-image :src="img16" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        Dude going to Irani cafe will never be fun without you. Even the chai seems tasteless without my fav person. Let's make a deal, next time you come to India, we will first go to Irani Cafe for Cheese Masala Omellete and Chaiiii 😌
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Durga Cafeee!" placement="top">
                                <el-card>
                                    <el-image :src="img17" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        This place has good food, great TV, and a Cute Manager as well🥰. "Shruti kaha khane jaana hai?" "Let's go to Durga" "Chalo!!": Ekdum Short and Sweet agreement it used to be whenever Durga ka naam aata tha 😁.
                                        What I loved about this place is everytime we used to try new food and everytime it turned out to be the best. It was your fav place to Hangout I guess. Yaha pe you introduced me to Kenny Seb ke standup vidoes and 
                                        I just loveeed his comedy. Yaad hai remote used to be with us all the time 🤣. We watched Bhagam Bhag too here. Our frequent visits to Durga was my sabse pasandita task.
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Visa Interview Scheduled ✔️" placement="top">
                                <el-card>
                                    <el-image :src="img19" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        This day was one relief wali din after many depressing days cause finally iss morning ko I got a call from you saying ki Visa Appointment is Scheduled for so on so date. I was sooo happy yaar cause you were finally relieved.
                                        Fir evening ko we met and went to Lenskart (Happy Spending). You gave me Momo treat too. I saw you smile after almost a week & that made my day. One the best memories
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="One More Wati Aam rass?" placement="top">
                                <el-card>
                                    <el-image :src="img20" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        Man you could have almost killed me that day cause I pranked you good 🤣🤣. You feel for it so easily and drank 2 to 3 bowls of aam rass more than you intended.
                                        But we had such good food after so long yaar and bohot enjoy kiya tha uss din bhi. I wore your fav pink t-shirt for the first time tab. We went home then while listening to Paar chan de 🥰
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Botim Zindabaad" placement="top">
                                <el-card>
                                    <el-image :src="img21" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        Once again adding to the list of failed movie nights, here is Afwaah, which we will never know if it was good or bad cause we stopped watching after 2 3 scenes only 🤣.
                                        It was one sad video call though. I don't remeber why but I remember it being sad. Ohh I guess we talked about you coming to India but not in Pune. 
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="Me being a Chinese" placement="top">
                                <el-card>
                                    <el-image :src="img22" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        Yaar I remeber crying on this call because mai bohot frustrate ho gaya tha due to conjunctivitis. I have never cried in front of any of my friends, except you. That is how much comfortable I am around you. You made me realise that it is okay for me to be vulnerable once in a while and it is okay to cry. You alwyas helped me out in so many ways that no one ever could. I am so gald that I met you for you have made me a better person in so many ways.
                                        Uss din bhi tujh se baat karke I felt so light and happy automatically. It's safe to say that talking to you only cured me before any medicine could 🤗
                                        Your cutieee ONE FANG smile ahhhhhhhh... It's the bestttttttt  
                                    </h3></el-card>
                            </el-timeline-item>

                            <el-timeline-item timestamp="104 not out" placement="top">
                                <el-card>
                                    <el-image :src="img23" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        This call will always be the closest to my heart. I was bimaar, weakness tha uske upar and travel bhi karna tha. But isse bhi upar I was very scared to travel in a Bus, wo bhi itne bimaari me. I texted you about it and you quickly called me uss time pe even in your busy schedule. You stayed on the call for 30+ mins just to make me feel good & safe. I don't what I did to deserve your love but I am so grateful for that. I always will be. A part of you will always remain with me. Thanks to your call uss raat ko I was able to travel with very less fear🤗. Thank You so much for always inspiring me to be kind and caring towards others. You da Best Cutieee 🥰  
                                    </h3></el-card>
                            </el-timeline-item>


                            <el-timeline-item timestamp="Machurian Momos and Lemon Iced Tea" placement="top">
                                <el-card>
                                    <el-image :src="img24" @load="onImgLoad"></el-image>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>Shrutiii...This was just a long way of saying I miss you and I was sooo lucky to have your Love. I don't have to climb a mountain or swim across the ocean to be with you cause you are always with me, in my thoughts, in my dreams & in my heart❤️. You deserve more than I could possibly give you, but everything I have is yours.
                                        "Enikya ninne ishtam aana, Shrutiii". You are one of the strongest persons I have ever known. It must be so hard being away from your family, comfort of your home, friends and country, but you are handling it incredibly well. Just remember that you will never ever be alone. Some days will be fun, some would be tough, but I promise I will be there for you whenever you need me. Am Just a call away.  
                                    </h3>
                                </el-card>
                            </el-timeline-item>

                            <el-timeline-item>
                                <el-card>
                                    <h3>
                                        So these were the "23 out of a million" my most cherished memories of us which 
                                        I wanna dedicate to you on this special occasion. 
                                        Happiest Birthday Dear!! 
                                        Love, now and always, Sada
                                    </h3></el-card>
                            </el-timeline-item>
                            
                        </el-timeline>
                    </transition>
                </div>
            </el-col>
        </el-row>

    </div>
</template>

<script>
    // Loading effect component
    import Loading from 'vue-loading-overlay';
    import 'vue-loading-overlay/dist/vue-loading.css';
    // Images
    // TODO : Put your images in /src/assets, and import them accordingly.
    import img1 from '../assets/1.jpg'
    import img2 from '../assets/2.jpg'
    import img3 from '../assets/3.jpg'
    import img4 from '../assets/4.jpg'
    import img5 from '../assets/5.jpg'
    import img6 from '../assets/6.jpg'
    import img7 from '../assets/7.jpg'
    import img8 from '../assets/8.jpg'
    import img9 from '../assets/9.jpg'
    import img10 from '../assets/10.jpg'
    import img11 from '../assets/11.jpg'
    import img12 from '../assets/12.jpg'
    import img13 from '../assets/13.jpg'
    import img14 from '../assets/14.jpg'
    import img15 from '../assets/15.jpg'
    import img16 from '../assets/16.jpg'
    import img17 from '../assets/17.jpg'
    //import img18 from '../assets/18.jpg'
    import img19 from '../assets/19.jpg'
    import img20 from '../assets/20.jpg'
    import img21 from '../assets/21.jpg'
    import img22 from '../assets/22.jpg'
    import img23 from '../assets/23.jpg'
    import img24 from '../assets/24.jpg'


    export default {
        name: "Messages",
        data() {
            return {
                // Display Timeline
                showTimeline: false,
                // Images
                // TODO : Modify the variables to cooperate with your images
                img1: img1,
                img2: img2,
                img3: img3,
                img4: img4,
                img5: img5,
                img6: img6,
                img7: img7,
                img8: img8,
                img9: img9,
                img10: img10,
                img11: img11,
                img12: img12,
                img13: img13,
                img14: img14,
                img15: img15,
                img16: img16,
                img17: img17,
                //img18: img18,
                img19: img19,
                img20: img20,
                img21: img21,
                img22: img22,
                img23: img23,
                img24: img24,
                
                
                
                imagesLoaded: 0,
                // TODO : Modify this number (totalImages) to the images you use in the content
                totalImages : 23,
                // Loader
                loaderLoading: true,
                loaderColor: "#dd6161",
                loaderOpacity: 1,
                loaderStyle: "dots",
                loaderHeight: 60,
                loaderWidth: 60,
                loaderFullPage: false
            }
        },
        components: {
            Loading
        },
        methods: {
            goBack() {
                this.$router.go(-1);
            },
            // This is a dump version of loading function,
            // feel free to change it to a more elegant implementation.
            onImgLoad() {
                this.imagesLoaded += 1;
                if (this.imagesLoaded === this.totalImages) {
                    console.log("Images Loaded");
                    setTimeout(() => this.loaderLoading = false, 500);
                    setTimeout(() => this.showTimeline = true, 800);
                }
            }
        }
    }
</script>

<style scoped>
    .messages_timeline {
        width: 80%;
        height: 83vh;
        margin-left: auto;
        margin-right: auto;
    }

    .back_button {
        margin-top: 15px;
        position: absolute;
    }
</style>