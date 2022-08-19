<template>
  <div class="hero flex center-column-top">
    <div class="container flex center-column-top">
      <div class="title flex center full-width hero">
        <div class="name flex full-width">
          <h1>Alexandr Borecky</h1>
          <div class="image"></div>
        </div>
        <div class="links full-width">
            <heroLink
              pageSection="#about"
              sectionTitle="About"
            />
            <heroLink 
              pageSection="#films"
              sectionTitle="Films"
            />
            <heroLink 
              pageSection="#contact"
              sectionTitle="Contact"
            />
            <div class="hr-line"></div>
        </div>
      </div>

      <div class="films hero flex column" id="films">
        <h2>Films to watch</h2>
        <div class="film-row flex">
          <a @click="untoldModal ()" class="thumb-snap">
          <filmThumbnail class="untold-pieces" 
            filmTitle="Untold Pieces"
            thumbnail="https://ik.imagekit.io/alexborecky/personal_web/Full_HD-min_96VrddI2e.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1660911454350"
            status="Coming 2022"
          />
          </a>
          <a @click="originModal ()" class="thumb-snap">
          <filmThumbnail 
            filmTitle="Origin"
            thumbnail="https://ik.imagekit.io/alexborecky/personal_web/1000x563-min_FfsKVX7ac.png?ik-sdk-version=javascript-1.4.3&updatedAt=1659616805474"
            status="Watch now"
          />
          </a>
          <div class="more-teaser flex middle">
            <p>More coming</p>
          </div>
        </div>
      </div>

      <div class="about flex" id="about">
        <div class="main-section">
          <h2>Alexandr Borecky</h2>
          <img src="https://ik.imagekit.io/alexborecky/personal_web/IMG_4350-min_3TFlJnsLT.jpeg?ik-sdk-version=javascript-1.4.3&updatedAt=1659616811632" alt="">
        </div>
        <hr>
        <div class="description">
          <p>Award winning director and actor Alexandr Borecky, currently based in Prague is starting to make his way to the industry despite his family's non-artistic background. His debut as a director and producer can be seen in his short film Origin, with which he has won several awards and now follows up with another project Untold Pieces which is planned to be released in late 2022.</p>
          <a class="close-button" target="_blank" href="https://www.imdb.com/name/nm8879254/?ref_=tt_cl_t_2">Read whole bio</a>
        </div>
      </div>

      <div class="contact flex column middle" id="contact">
        <div class="statement flex column center">
          <h2>Contacts</h2>
          <p>Looking for a director or a producer? Let's chat!</p>
        </div>
        <ul class="flex">
          <li><a target="_blank" href="https://www.instagram.com/alex.borecky/">Instagram</a></li>
        </ul>
        <p><small>For representation and other business inquiries, please contact me via email boreckyalex@gmail.com</small></p>
      </div>
    </div>
    <div class="modals">
      <!-- UNTOLD PIECES -->
        <div class="modal flex middle column" v-if="piecesModal">
        <filmWindow id="untold-pieces"
          thumbnail="https://ik.imagekit.io/alexborecky/personal_web/Full_HD-min_96VrddI2e.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1660911454350"
          filmTitle="Untold Pieces"
          filmLink=""
          actionLine="Coming 2022"
          tagOne="Drama, Comedy"
          year="2022"
          description="After learning about his mother's death, Casey is left with feelings of guilt and confusion as he finds himself relieved about the news. With his friend Jenny, he is trying to find out what is an appropriate reaction to someone's death."
        />
        <!-- <div class="close-cover" @click="untoldModal ()"></div> -->
        <a class="modal-close flex center" @click="untoldModal ()">
        <svg width="24" height="24" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M25 7L7 25" stroke="white" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M25 25L7 7" stroke="white" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
          CLOSE INFO
        </a>
        </div>
        <!-- ORIGIN -->
        <div class="modal flex middle column" v-if="oriModal">
        <filmWindow id="origin"
          thumbnail="https://ik.imagekit.io/alexborecky/personal_web/1000x563-min_FfsKVX7ac.png?ik-sdk-version=javascript-1.4.3&updatedAt=1659616805474"
          filmTitle="Origin"
          filmLink="https://youtu.be/xLExJm6A13A"
          actionLine="Watch now"
          tagOne="Drama"
          year="2021"
          description="Three friends, that had known each other since they were little kids, have decided to spend a night out together. Leo, a person that relies heavily on their friendship, is realising how much he has been lacking behind in his life when he sees his how much his friends grew as people, outside their little circle. This makes Leo reconsider his approach to life and also makes him think about how much relying on the friendship has hold him back."
        />
        <!-- <div class="close-cover" @click="originModal ()"></div> -->
        <a class="modal-close flex center" @click="originModal ()"><svg width="24" height="24" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M25 7L7 25" stroke="white" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M25 25L7 7" stroke="white" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>CLOSE INFO</a>
        </div>

      <div class="modal flex middle column" v-if="modal">
        <div class="modal-window flex column" id="bio">
          <h2>Biography</h2>
            <p>An award winning director and actor Alexandr Borecky, currently based in Prague is starting to make his way to the industry despite his family's non-artistic background. His debut as a director and producer can be seen in his short film Origin, with which he has won several awards and now follows up with another project Untold Pieces which is planned to be released in late 2022. <br> Alexandr Borecky was born Czech Republic, and raised in Prague, where he is working on several projects as actor, writer and director. He first encountered acting during drama classes in high school. After few small school productions, Alexandr moved to Atlanta at the age of 17 where he first encountered musical theatre and had a chance to perform in productions such as Les Misérables, Mamma Mia and Grease.<br>While studying at Charles University Alexandr took classes of theatrical improvisation. That's where he was offered to study at Prague Conservatory of Acting which he eventually refused and continued at Charles University. He left the university three years later, started a proper theatrical training and decided to pursue acting as a career. During this stage of the training he was able to take part in few theatrical productions in Prague. <br> In 2017 he moved to Los Angeles to get a proper on-camera acting training which he received in form of individual classes. After further consideration, research and interviews he decided to adopt a method technique for his future work, following the footsteps of his role models Daniel Day-Lewis, Javier Bardem or Joaquin Phoenix.</p>         
        </div>
        <a class="modal-close flex middle close" @click="aboutModal()">
        <svg width="24" height="24" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M25 7L7 25" stroke="white" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M25 25L7 7" stroke="white" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>CLOSE INFO</a>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  methods: {
    aboutModal () {
      if(this.modal == false){
                this.modal = true
            } else {
                this.modal = false
            }
    },
    untoldModal () {
      if(this.piecesModal == false){
                this.piecesModal = true
            } else {
                this.piecesModal = false
            }
    },
    originModal () {
      if(this.oriModal == false){
                this.oriModal = true
            } else {
                this.oriModal = false
            }
    },
  },
  data () {
        return {
            modal: false,
            piecesModal: false,
            oriModal: false,
            dialog: false
        }
    },
    
}
</script>

<style lang="scss">

.title {
  height: 100vh;
  align-items: flex-end;
  .name {
    height: 840px;
    position: relative;
    @media (max-width: 1600px) {
        height: 720px;
    }
    .image {
      position: absolute;
      bottom: 0;
      width: 65%;
      height: 85%;
      z-index: 1000;
      background-size: cover;
      background-position: center;
      background-image: url(https://ik.imagekit.io/alexborecky/personal_web/Screenshot_2022-08-04_at_13.31.08__2__K6sLJnHWP.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1659616722559);
    }
    h1 {
      position: absolute;
      right: 0;
      z-index: 1001;
    }
  }
  .links {
      position: absolute;
      height: 100%;
      top: 0;
      left: 0;
      width: 100vw;
      .line {
        width: 1px;
        height: 400px;
      }
      .hr-line {
        width: 1px;
        height: 60vh;
        background-color: rgba($color: #fff, $alpha: .24);
        top: 0;
        left: 15vw;
      }
      a, .hr-line {
        position: absolute;
      }
      a:nth-child(1) {
        bottom: 0px;
        right: 10vw;
        display: flex;
        flex-flow: column;
        align-items: center;
        .line {
          width: 1px;
          height: 400px;
        }
      }
      a:nth-child(2) {
        top: 10vh;
        right: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        .line {
          width: 60vw;
          height: 1px;
        }
      }
      a:nth-child(3) {
        bottom: 10vh;
        left: 30vw;
        display: flex;
        justify-content: center;
        align-items: center;
        p {
          order: 2;
        }
        .line {
          width: 40vw;
          height: 1px;
          .inner-line {
            left: 0 !important;
          }
        }
      }
    }
    @media (max-width: 500px) {
      flex-flow: column;
      .name {
        margin-top: 40px;
        height: auto;
        flex-flow: column;
        h1, .image {
          position: relative;
        }
        .image {
          height: 50vh;
          width: 100%;
          margin: 16px 0;
        }
        h1 {
          font-size: 48px;
          left: 0;
          letter-spacing: 4px;
        }
      }
      .links {
        position: relative;
        display: flex;
        height: auto;
        width: 100%;
        justify-content: space-between;
        a {
          position: relative;
          top: 0 !important;
          left: 0 !important;
          right: 0 !important;
          .line {
            display: none !important;
          }
        }
        .hr-line {
          display: none;
        }
      }
    }
}

.films {
  h2 {
    margin: 24px 0;
  }
  min-height: 60vh !important;
  justify-content: center;
  .untold-pieces {
    .info-bar {
      a:nth-child(1) {
        opacity: .4 !important;
        img {
          display: none;
        }
      }
    }
  }
  .film-row {
    justify-content: space-between;
    height: 350px;
    @media (max-width: 1680px) {
        height: 24vh;
    }
    .thumb-snap {
      width: 40%;
      border-radius: 8px;
      cursor: pointer;
      height: 100%;
    }
  }
  .more-teaser {
    border-radius: 8px;
    border: solid 1px rgba($color: #fff, $alpha: .24);
    width: 17%;
    height: 100%;
    p {
      opacity: .56;
    }
  }
  @media (max-width: 550px) {
    .film-row {
      flex-flow: column;
      height: auto;
      .thumb-snap {
        width: 100% !important;
        margin: 16px 0;
        height: 200px;
      }
      .more-teaser {
        width: 100%;
        height: 100px;
      }
    }
  }
}

.about {
  max-height: 700px !important;
  min-height: none !important;
  margin: 80px 0;
  justify-content: space-between;
  .main-section, .description {
    width: 45%;
  }
  hr {
    opacity: .24;
  }
  .main-section {
    h2 {
      font-size: 72px;
      font-weight: 300;
    }
    img {
      width: 100%;
      height: auto;
      margin-top: 80px;
    }
  }
  .description {
    justify-content: space-between;
    display: flex;
    flex-flow: column;
    p {
      font-size: 24px;
      font-weight: 400;
      line-height: 56px;
      letter-spacing: 2px;
      text-align: left;
      opacity: .8;
    }
    .close-button {
      background-color: rgba($color: #fff, $alpha: .16) !important; 
      color: #fff !important;
      font-weight: 700 !important;
    }
  }
  @media (max-width: 550px) {
    flex-flow: column;
    max-height: none !important;
    .main-section, .description {
      width: 100%;
    }
    .main-section {
      img {
        margin-top: 24px;
      }
      h2 {
        font-size: 40px;
      }
    }
    hr {
      display: none;
    }
    .description {
      p {
        font-size: 16px;
        line-height: 32px;
        letter-spacing: 1px;
        margin: 16px 0;
      }
    }
  }
}

.modal {
    background: rgba(0, 0, 0, 0.58);
    backdrop-filter: blur(8px);
    position: fixed;
    z-index: 1005;
    top: 0;
    left: 0;
    height: 100vh !important;
    width: 100%;
    p {
      opacity: .8;
    }
    .close-cover {
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0;
      left: 0;
      z-index: 1;
      background-color: red;
    }
    .modal-window {
      text-align: left !important;
      height: auto;
      width: 70%;
      padding: 40px;
      background-color: black;
      border-radius: 16px;
      z-index: 10000 !important;
      p {
          margin: 8px 0;
          font-size: 14px;
          line-height: 32px;
      }
  }
  .modal-close {
    margin: 24px !important;
    cursor: pointer;
    font-size: 16px;
    letter-spacing: 2px;
    color: white;
    transition: .2s ease-in;
    svg {
      margin-right: 8px;
    }
    &:hover {
      opacity: .64;
    }
  }
  @media only screen and (max-width: 1024px) {
      .modal-window {
          width: 60%;
          padding: 40px;
      }
  }
  @media only screen and (max-width: 540px) {
      .modal-window {
          width: 90%;
          padding: 32px 16px;
      }
  }
  @media only screen and (max-width: 370px) {
      .modal-window {
          width: 90%;
          height: 90%;
      }
  }
}


#untold-pieces {
  .thumbnail-section {
    .film-info {
      a {
        padding: 8px 16px;
        background-color: transparent !important;
        border: solid 1px rgba($color: #fff, $alpha: .24) !important;
        color: rgba($color: #fff, $alpha: .56) !important;
        border-radius: 8px;
        text-decoration: none;
        font-weight: 400;
        pointer-events: none;
     }
    }
  }
}

#bio {
  p {
    font-size: 20px;
    line-height: 40px;
    opacity: .8;
  }
}

.close-button {
  padding: 8px 16px;
  background-color: transparent !important;
  border: solid 1px rgba($color: #fff, $alpha: .24) !important;
  color: rgba($color: #fff, $alpha: .8) !important;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 400;
  width: 160px;
  text-align: center;
}

.contact {
  height: 50vh;
  h2 {
    font-size: 40px;
    margin: 24px 0;
    letter-spacing: 4px;
  }
  p {
    opacity: .8;
    font-size: 16px;
    letter-spacing: 1px;
    small {
      opacity: .64;
    }
  }
  ul {
    padding: 0 !important;
    margin: 40px;
    list-style: none;
    a {
      font-size: 20px;
      letter-spacing: 2px;
      margin: 16px;
      transition: .3s ease;
      &:hover {
        opacity: .4;
      }
    }
  }
  @media (max-width: 550px) {
    text-align: center;
  }
}

</style>
