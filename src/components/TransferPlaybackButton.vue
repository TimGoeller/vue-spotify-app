<template>
  <div id="transfer-playback-button" v-on:click="click">
    <button :class="{'active': isActive}">
      <div>
        <h2>Play here</h2>
        <span>Stop playback on active device and start playback here</span>
      </div>
    </button>
  </div>
</template>

<script>
export default {
  name: 'transfer-playback-button',
  props: {
    isActive: {
      type: Boolean,
      default: true
    }
  },
  methods: {
      click: function() {
          this.$emit('clicked')
      }
  }
}
</script>

<style lang="scss" scoped>

  @import '../assets/settings.scss';              

  #transfer-playback-button button{
    width: 100%;
    height: 70px;
    background-color: $light-background;
    justify-content: center;
    align-items: center;
    display: flex;
    border-radius: 90px;
    margin: 15px 0 15px 0;
    border:none;
    outline: none;

    opacity: 0.6;

    &.active {
      opacity: 1;

      &:hover, &:focus {
        border: 3px solid $secondary-color;
        cursor: pointer;
      }
    }

    &:hover, &:focus {
      box-shadow: 2px 2px 20px -4px rgba(0,0,0,0.90);
    }  

    h2 {
      @include md {
        font-size: 2em;
      }
      font-size: 1.8em;
      margin: 0;
      font-weight: 400;
      color: $secondary-color;
    }

    span {
      @include md {
        font-size: 1em;
      }
      font-size: 0.8em;

      
    }

    

  }
</style>
