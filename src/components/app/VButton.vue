<template>
  <button class="v-button" :class="[color, shape, size]">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "VButton",
  props: {
    color: {
      validator(s) {
        //return ["yellow"].includes(s);
        return ["yellow", "orange", "red", "blue", "light-blue", "purple", "black", "white"].includes(s);
      },
      default: "yellow",
    },
    shape: {
      validator(s) {
        return ["round", "square"].includes(s);
      },
      default: "square",
    },
    size: {
      validator(s) {
        return ["small", "medium", "height_45", "height_2rem"].includes(s);
      },
      default: "medium",
    },
    hoverText: {
      type: String,
      default: ''
    }
  },
};
</script>

<style lang="scss" scoped>
.v-button {
  cursor: pointer;
  border: none;
  box-shadow: 0 3px 6px rgba(#000, 0.16);
  font-family: "Gotham Book";
  font-size: 25px;
  line-height: 38px;
  padding: 0 20px;
  transition: 175ms ease;

  &:active {
    box-shadow: 0 3px 3px rgba(#000, 0);
  }

  &:focus {
    outline: none;
  }

  a:hover {
    text-decoration: none;
  }
}

.yellow {
  background: #ffe300;

  &:hover {
    background: #fffb00;
    filter: drop-shadow(0 1px 5px);
  }

  &:active {
    background: #ffd000;
  }
}

.orange {
  background: #E8B740;

  &:hover {
    background: #ffd675;
    filter: drop-shadow(0 1px 5px);
  }

  &:active {
    background: #ffd675;
  }
}

.red {
  background: #F11E24;

  &:hover {
    background: #ff7075;
    filter: drop-shadow(0 1px 5px);
  }

  &:active {
    background: #ff7075;
  }
}

.blue {
  background: #134BCE;

  &:hover {
    background: #3773ff;
    filter: drop-shadow(0 1px 5px);
  }

  &:active {
    background: #3773ff;
  }
}

.purple {
  background: #CB65C8;

  &:hover {
    background: #ffa8fc;
    filter: drop-shadow(0 1px 5px);
  }

  &:active {
    background: #ffa8fc;
  }
}

.light-blue {
  background: #15BCDE;

  &:hover {
    background: #57e3ff;
    filter: drop-shadow(0 1px 5px);
  }

  &:active {
    background: #57e3ff;
  }
}

.black {
  background: #000000;

  a {
    color: white !important;
  }

  &:hover {
    background: #000000;
    filter: drop-shadow(0 1px 5px);
  }

  &:active {
    background: #000000;
  }
}

.round {
  border-radius: 50px;
}

.medium {
  height: 60px;
}

.height_45 {
  height: 45px;
  line-height: 48px;
}
.height_2rem {
  height: 2rem;
  line-height: 2rem;
  font-size: 1rem;
}

.small {
  height: 30px;
}
</style>
