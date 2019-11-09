<template>
  <div class="shadow flex flex-col rounded gxCalendar p-5">
    <div class="w-full flex justify-between items center">
      <button class="font-bold">&lt;</button>
      <p class="font-bold">{{monthString}}</p>
      <button class="font-bold">></button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
    week: {
      type: String,
      default: "long"
    },
    year: {
      // https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DateTimeFormat
      type: String,
      default: "numeric"
    },
    month: {
      type: String,
      default: "long"
    },
    day: {
      type: String,
      default: "numeric"
    }
  },
  data() {
    return {
      innerDay: new Date().getDate(),
      innerMonth: new Date().getMonth(),
      innerYear: new Date().getFullYear()
    };
  },
  computed: {
    dateObject() {
      return new Date(this.innerYear, this.innerMonth, this.innerDay);
    },
    monthString() {
      const locale = "es-ES";
      const options = {
        day: this.day,
        year: this.year,
        month: this.month
      };
      const dateFormatter = new Intl.DateTimeFormat(locale, options);
      return dateFormatter.format(this.dateObject);
    },
    formatterParts() {
      const locale = "es-ES";
      const options = {
        day: this.day,
        year: this.year,
        month: this.month
      };
      const dateFormatter = new Intl.DateTimeFormat(locale, options);
      return dateFormatter.formatToParts(this.dateObject);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.gxCalendar {
  width: 358px;
  height: 374px;
}
</style>
