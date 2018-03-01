<template>
  <div>
    <div class="card" :style="{background: '#ccc'}">
      <section class="movie_image">
        <img class="movie_poster" :src="`https://image.tmdb.org/t/p/w45/${info.poster_path}`" alt="As Above So Below" />
      </section>

      <section class="center">
        <div class="about_movie">
          <h3>{{ info.title }}</h3>
          <div class="movie_info">
            <p>{{ info.release_date }}</p>
            <p>1h 33min</p>
            <p>Horror, Mystery, Thriller </p>
          </div>
          <div class="movie_desc">
            <p>When a team of explorers ventures into the catacombs that lie beneath the streets of Paris, they uncover the dark secret that lies within this city of the dead.</p>
          </div>

          <button class="watch"> <svg viewBox="0 0 30.051 30.051" style="enable-background:new 0 0 30.051 30.051;" xml:space="preserve">
          <path d="M19.982,14.438l-6.24-4.536c-0.229-0.166-0.533-0.191-0.784-0.062c-0.253,0.128-0.411,0.388-0.411,0.669v9.069
            c0,0.284,0.158,0.543,0.411,0.671c0.107,0.054,0.224,0.081,0.342,0.081c0.154,0,0.31-0.049,0.442-0.146l6.24-4.532
            c0.197-0.145,0.312-0.369,0.312-0.607C20.295,14.803,20.177,14.58,19.982,14.438z" />
          <path d="M15.026,0.002C6.726,0.002,0,6.728,0,15.028c0,8.297,6.726,15.021,15.026,15.021c8.298,0,15.025-6.725,15.025-15.021
            C30.052,6.728,23.324,0.002,15.026,0.002z M15.026,27.542c-6.912,0-12.516-5.601-12.516-12.514c0-6.91,5.604-12.518,12.516-12.518
            c6.911,0,12.514,5.607,12.514,12.518C27.541,21.941,21.937,27.542,15.026,27.542z" />
        </svg> Watch Now!</button>
              <button class="watchlist"><svg viewBox="0 0 401.994 401.994" style="enable-background:new 0 0 401.994 401.994;" xml:space="preserve">
          <path d="M394,154.175c-5.331-5.33-11.806-7.994-19.417-7.994H255.811V27.406c0-7.611-2.666-14.084-7.994-19.414
            C242.488,2.666,236.02,0,228.398,0h-54.812c-7.612,0-14.084,2.663-19.414,7.993c-5.33,5.33-7.994,11.803-7.994,19.414v118.775
            H27.407c-7.611,0-14.084,2.664-19.414,7.994S0,165.973,0,173.589v54.819c0,7.618,2.662,14.086,7.992,19.411
            c5.33,5.332,11.803,7.994,19.414,7.994h118.771V374.59c0,7.611,2.664,14.089,7.994,19.417c5.33,5.325,11.802,7.987,19.414,7.987
            h54.816c7.617,0,14.086-2.662,19.417-7.987c5.332-5.331,7.994-11.806,7.994-19.417V255.813h118.77
            c7.618,0,14.089-2.662,19.417-7.994c5.329-5.325,7.994-11.793,7.994-19.411v-54.819C401.991,165.973,399.332,159.502,394,154.175z" />
        </svg>
        Add to watchlist!</button>
        </div>
      </section>


      <!-- <svg class="wavy" viewBox="0 0 500 500" preserveAspectRatio="xMinYMin meet">
        <path d="M0,100 C150,200 350,0 500,100 L500,00 L0,0 Z" style="stroke: none;"></path>
      </svg> -->
    </div>
  </div>
</template>

<script>
  export default {
    props: ['info'],
    data() {
      return {
      }
    },
    watch: {
    }
  }
</script>

<style lang="scss" scoped>
.card {
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  // max-width: 550px;
  width: 100%;
  margin: 5px;
  margin-left: 18px;
  height: 200px;
  border-radius: 4px;
  position: relative;
  overflow: hidden;
  @media (max-width: 520px) {
    background: rgba(0, 0, 0, .3);
    display: flex;
    flex-direction: column;
    height: auto;
    box-shadow: 4px 4px 10px rgba(255, 255, 255, .2);
  }
  .movie_image {
    // min-width: 80px;
    padding: 0px 10px;
    display: flex;
    position: relative;
    z-index: 99;
    @media (max-width: 520px) {
      display: flex;
      flex-basis: auto;
      margin: 0 auto;
      height: 200px;
      padding: 10px 0;
      margin-bottom: 25px;
      overflow: hidden;
    }
    .movie_poster {
      height: 100%;
      height: auto;
      margin: 0px;
    }
  }
  .center {
    display: flex;
    align-items: center;
    vertical-align: center;
    position: relative;
    z-index: 99;
    @media (max-width: 520px) {
      padding: 10px 0px;
    }
  }
  .about_movie {
    flex-basis: 100%;
    padding: 0px 10px;
    position: relative;
    z-index: 99;
    @media (max-width: 520px) {
      align-items: center;
      text-align: center;
    }
    h3 {
      color: #fff;
      font-size: 25px;
      margin-bottom: 10px;
      margin-top: 0px;
      text-align: center;
    }
    .movie_info {
      display: flex;
      justify-content: space-between;
      @media (max-width: 520px) {
        justify-content: space-around;
      }
      font-size: 14px;
      color: rgba(255,
      255,
      255,
      .6);
    }
    .movie_desc {
      font-size: 16px;
      margin-top: 25px;
      margin-bottom: 25px;
      color: rgba(255, 255, 255, 1);
      position: relative;
      z-index: 99;
    }
  }
  /* wawy svg */
  .wavy {
    position: absolute;
    bottom: calc(0px);
    fill: rgba(230, 39, 20, 1);
    transform: rotate(180deg);
    z-index: 0;
  }
  .watch {
    position: relative;
    z-index: 99;
    background: rgba(255, 255, 255, .3);
    color: #fff;
    border: none;
    border-radius: 4px;
    padding: 5px 10px;
    outline: none;
    cursor: pointer;
    font-size: 15px;
    transition: all .3s;
    &:hover {
      background: rgba(255, 255, 255, .2);
    }
    svg {
      width: 15px;
      height: 15px;
      position: relative;
      top: 2px;
      fill: #fff;
    }
  }
  .watchlist {
    position: relative;
    z-index: 99;
    background: transparent;
    color: rgba(255, 255, 255, .9);
    border: none;
    border-radius: 4px;
    padding: 5px 10px;
    outline: none;
    cursor: pointer;
    font-size: 15px;
    transition: all .3s;
    &:hover {
      color: rgba(255, 255, 255, 1);
    }
    svg {
      width: 15px;
      height: 15px;
      position: relative;
      top: 2px;
      fill: rgba(255, 255, 255, 1);
    }
  }
}

</style>

