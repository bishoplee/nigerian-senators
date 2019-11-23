<template>
  <div class="wrapper">
    <div class="profile">
      <img
        src="https://res.cloudinary.com/luthfulahi/image/upload/q_auto/v1574501556/download_arqzve.jpg"
        class="thumbnail"
      />
      <h3 class="name">{{ detail.name }}</h3>
      <hr />
      <div class="description">
        <a :href="`tel:${detail.phone}`">
          <i class="fa fa-phone"></i> Call {{ detail.phone }}
        </a>
      </div>
      <div class="description">
        <a :href="`sms:${detail.phone}`">
          <i class="fa fa-envelope"></i> Send SMS to {{ detail.name }}
        </a>
      </div>
      <div class="description">
        <a target="_blank" :href="`mailto:${detail.email}`">
          <i class="fa fa-envelope"></i> Send a mail to {{ detail.email }}
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  props: {
    detail: Object
  }
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
hr {
  margin: 15px;
}
a {
  color: black;
  text-decoration: none;
  text-transform: uppercase;
}

a:hover {
  color: #555;
}

a:active {
  color: black;
}

a:visited {
  color: black;
}

// ------------------------------------------------
$shadow: 0 13px 26px rgba(#000, 0.2), 0 3px 6px rgba(#000, 0.2);

// ------------------------------------------------

.wrapper {
  flex: auto;
  background: #fdfeff;
  transition: background 0.6s ease;
  border-radius: 10px;
  padding: 20px 20px 20px 20px;
  margin: 1em;
  box-shadow: 0 8px 40px rgba(#000000, 0.2);

  .top-icons {
    i {
      color: #080911;
      &:nth-of-type(1) {
        float: left;
      }
      &:nth-of-type(2) {
        float: right;
      }
      &:nth-of-type(3) {
        float: right;
        padding-right: 0.8em;
      }
    }
  }
  .profile {
    margin-top: 2.2em;
    position: relative;

    &:after {
      width: 100%;
      height: 1px;
      content: " ";
      display: block;
      margin-top: 1.3em;
      background: #e9eff6;
    }
    .thumbnail {
      width: 124px;
      height: 124px;
      display: flex;
      margin-left: auto;
      margin-right: auto;
      margin-bottom: 1.5em;
      border-radius: 100%;
      box-shadow: $shadow;
    }
    .name {
      color: #2d354a;
      font-size: 24px;
      font-weight: 600;
      text-align: center;
    }

    .title {
      color: #7c8097;
      font-size: 0.75em;
      font-weight: 300;
      text-align: center;
      padding-top: 0.5em;
      padding-bottom: 0.7em;
      letter-spacing: 1.5px;
      text-transform: uppercase;
    }

    .description {
      color: #080911;
      font-size: 14px;
      font-weight: 300;
      text-align: center;
      margin-bottom: 2em;
    }
  }
}
</style>
