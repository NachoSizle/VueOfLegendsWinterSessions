<template>
  <div class="card--container">
    <h1>{{ character.champion_name }}</h1>
    <img :src="character.champion_splash" alt="">
  </div>
</template>

<script>
export default {
  name: 'CharacterCard',
  props: {
    character: Object,
  },
};
</script>

<style scoped lang="scss">
  .card {
    &--container {
      width: 100%;
      height: 100%;
      max-width: 320px;
      min-width: 295px;

      display: flex;
      flex-direction: column;
      justify-content: flex-start;

      border-radius: 20px;
      background-color: rgb(221, 220, 219);
      box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
    }

    &--container.expanded {
      max-width: 49%;

      @media (max-width: 1280px) {
        max-width: 55%;
      }

      @media (max-width: 1024px) {
        max-width: 70%;
      }

      @media (max-width: 768px) {
        max-width: 100%;
      }

      & .card {
        &--image {
          max-height: 100%;
          padding: 0;

          img {
            border-top-left-radius: 20px;
            border-top-right-radius: 20px;
          }
        }
        &--info {
          max-height: 100%;
        }
        &--title {
          margin-bottom: 2rem;
        }
        &--description {
          display: flex;
          justify-content: center;
          align-items: center;
          flex-direction: column;
          gap: 2rem;

          &-content {
            max-height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 2rem;

            img {
              max-width: 3rem;
              max-height: 3rem;
              border-radius: 50%;
            }

            &:last-of-type {
              gap: 0;
              width: 100%;
              justify-content: space-evenly;
            }
          }
          &-skill {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;

            cursor: pointer;

            &:hover {
              transform: scale(1.1);
            }
          }
        }
        &--actions {
          max-width: calc(100% - 2rem);
        }
      }
    }

    &--top-info {
      height: 100%;
      max-height: 2.5rem;

      position: absolute;

      display: flex;
      align-items: center;
      justify-content: space-between;

      padding: 0 0.5rem;
      padding-top: 1rem;

      &--icon {
        max-width: 32px;

        img {
          max-width: 32px;
          max-height: 32px;
          border-radius: 50%;
        }
      }
    }

    &--image {
      max-height: 189px;

      padding: 0;

      background-color: rgb(221, 220, 219);
      border-radius: 20px;

      img {
        max-width: 100%;
        max-height: 100%;
        border-top-left-radius: 20px;
        border-top-right-radius: 20px;
      }
    }

    &--info {
      position: relative;
      bottom: 2rem;

      height: 100%;
      max-height: 294px;

      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      align-items: flex-start;
    }

    &--icon-right {
      max-width: 3rem;
      max-height: 3rem;

      position: relative;
      right: 1rem;
      top: 1rem;
      align-self: flex-end;

      box-sizing: border-box;
      padding: 0.5rem;
      border-radius: 50%;
      background-color: rgb(221, 220, 219);

      img {
        max-width: 2rem;
        max-height: 2rem;
        box-sizing: border-box;
      }
    }

    &--title {
      text-align: left;
      text-transform: capitalize;

      margin: 0;
      margin-left: 1rem;
    }

    &--subtitle {
      text-align: left;
      text-transform: capitalize;

      margin: 0;
      margin-bottom: 1rem;
      margin-left: 1rem;
    }

    &--description {
      text-align: start;
      padding: 0 1rem;
    }

    &--actions {
      width: 100%;
      max-width: calc(320px - 2rem);
      height: 100%;
      max-height: 2.5rem;

      position: relative;
      bottom: 1.5rem;

      display: flex;
      align-items: center;
      justify-content: center;

      padding: 0 1rem;

      &-element {
        button {
          display: flex;
          justify-content: center;
          align-items: center;
          column-gap: 0.25rem;
          padding: 0.25rem 0.75rem;

          cursor: pointer;

          &.button--round {
            border-radius: 20px;
          }

          &:hover {
            background-color: rgb(221, 220, 219);
          }

          &:active {
            background-color: rgb(179, 177, 176);
          }
        }

        img {
          max-width: 1rem;
          max-height: 1rem;
        }
      }
    }
  }
</style>
