<template>
  <section>
  <div class="steps container is-fluid">

      <div :id="'item-sm-' + index" v-if="stp.id != 0" v-for="(stp, index) in steps" :data-clicked="stp.clicked | booleanfilt" :data-size="stp.size | booleanfilt" :index="index" :key="stp.id" class="column packery-item step">
        <article><nuxt-link :to="`/step/${stp.id}`">
        <div class="notification step is-pink-outline is-bold">
          <figure v-if="stp.image" class="sel image is-1by1">
          <img :src="stp.image">
          </figure>

                <div class="sel step-number">
         STEP {{stp.text}}
      </div> <h4 class="sel title"><fit-text class="list-name">{{ stp.heading }}</fit-text>
       <span class="sel productname">
         {{stp.productname}}
       </span>
</h4>

        </div></nuxt-link>
       </article>
      </div>

</div>
</section>
</template>
<script>
import fitText from '~/components/fitText.vue'
export default {
  props: ['steps'],
  components: {
fitText
    },
   filters: {
    booleanfilt(value) {
      return Boolean(value);
    }
  },
}
</script>
<style>
.list-name {color:RGBA(29,60,101,1.00) !important;font-weight:500;font-family: orpheuspro, Cambria, Cochin, Georgia, Times, Times New Roman,
    serif;}
.packery-item {
  display: inline-block;
    flex-direction: column;

}
.packery-item article {
  padding-right: 4px;
  padding-left: 4px;
  padding-top: 4px;
  padding-bottom: 4px;
  cursor: pointer;
}
.packery-item[data-clicked="true"] .notification {
  border: 6px solid #ffcdca;
  z-index: 101;
  transition: 0.3s all;
}
.notification.step {box-shadow: 4px 4px 10px rgba(255,255,255,.5)}

.packery-item[data-clicked="true"] .title {
  color: #ff3860;
}
  @media (min-width:100px) and (max-width: 468px) {
    .param-item {width:100% !important;}
    .title {
  letter-spacing: -.01vw;
}
  }
    @media (min-width:469px) and (max-width: 899) {
    .param-item {width:50% !important;}
        .title {
  letter-spacing: -.01vw;
}
  }
.packery-item[data-clicked="true"] .notification {
  box-shadow: 7px 9px 105px 0px rgba(0, 0, 0, 0.3);
  border-color: #ff3860;
  transition: 0.3s all ease-in-out;
  max-height: 90vh;
  overflow-y: hidden;
}
.description {
  padding-bottom: 16px;
}
.packery-item[data-clicked="true"] .description {
  overflow-y: scroll;
}
.packery-item[data-clicked="true"] .notification:hover {
  background: #fff;
  transform: scale(0.99);
  transition: 0.3s all;
  border-width: 8px;
}
.packery-item[data-clicked="true"] .notification:active {
  background: #fef3f2;
  transform: translateY(3px);
  transition: 0.05s all;
}
.packery-item[data-clicked="true"] .notification:hover h4.title {
  opacity: 0.7;
}
.packery-item[data-clicked="true"] .notification:active h4.title {
  opacity: 0.3;
}


@media (min-width: 200px) and (max-width: 1199px) {
  .packery-item,
  .packery-item[data-size="false"] {
    width: 100%;
  }
  .packery-item[data-size="true"],
  .active.packery-item[data-size="false"] {
    width: 100%;
  }
  .packery-item[data-size="2"] {
    width: 100%;
  }
}


@media (min-width: 1200px) and (max-width: 1800px) {
  .packery-item,
  .packery-item[data-size="false"] {
    width: 50%;
  }
  .packery-item[data-size="true"],
  .active.packery-item[data-size="false"] {
    width: 50%;
  }
  .packery-item[data-size="2"] {
    width: 50%;
  }
}

@media (min-width: 1801px) {
  .packery-item,
  .packery-item[data-size="false"] {
    width: 33%;
  }
  .packery-item[data-size="true"],
  .active.packery-item[data-size="false"] {
    width: 33%;
  }
  .packery-item[data-size="2"] {
    width: 33%;
  }
}
.step-intro .notification {
  border-color: #fff !important;
  background-color: #fff !important;
}

.productname {
  font-size: 14px;
  font-weight: 700 !important;
  color: #333;
  display: inline-block;
  letter-spacing: 0;

}
.notification .productname {  border-top:thin solid #DEC9C8;
  padding-top:12px;margin-top:12px; display:block;}
  .content,.notification {text-shadow: 0 2px 0 rgba(255, 255, 255, 0.6);}

</style>
