<template>
  <section>
    <header class="questn-header">Assessment</header>
    <div class="about">
      <ul>
        <li
          v-for="item in $options.filters.filteredQuestion(questions)"
          v-bind:key="item.id"
        >{{item.qst}}</li>
        <ul class="answers">
          <li>Option 1</li>
          <li>Option 2</li>
          <li>Option 3</li>
          <li>Option 4</li>
        </ul>
      </ul>
    </div>
    <div class="footer">
      <div>Q{{counter + 1}} / {{questions.length}}</div>
      <div>
        <button class="qustn-generator" v-if="counter< 9" v-on:click="counter += 1">Next &#8680;</button>
        <button class="qustn-generator" v-if="counter === 9">Submit</button>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
section {
  padding: 30px;
  .questn-header {
    background-color: rgba(69, 23, 113, 0.92);
    color: #ffffff;
    font-size: xx-large;
    padding: 20px;
  }
  .about {
    border: solid 2px rgba(69, 23, 113, 0.92);
    border-top: 0;
    color: rgba(69, 23, 113, 0.92);
    font-size: 20px;
    padding: 20px;
    ul {
      line-height: 3;
      list-style: none;
      .answers {
        padding-left: 10px;
        line-height: 2;
        list-style: circle;
      }
    }
  }
  .footer {
    background-color: rgba(69, 23, 113, 0.92);
    color: #fff;
    display: flex;
    justify-content: space-between;
    line-height: 2.5;
    padding: 5px 10px;
  }
}
</style>

<script>
function initialState() {
  return {
    counter: 0,
    questions: [
      {
        id: 1,
        qst: "Who was your childhood actor/actress crush?",
        category: "iceBreaker"
      },
      {
        id: 2,
        qst: "What’s your most embarrassing moment from your teen years?",
        category: "iceBreaker"
      },
      {
        id: 3,
        qst: "What’s the worst thing you ever did as a kid?",
        category: "iceBreaker"
      },
      {
        id: 4,
        qst: "What’s your silliest memory with your best friend?",
        category: "iceBreaker"
      },
      {
        id: 5,
        qst:
          "What did you get into the most trouble for with your parents as a kid?",
        category: "iceBreaker"
      },
      {
        id: 6,
        qst: "What’s the story of your first crush?",
        category: "iceBreaker"
      },
      {
        id: 7,
        qst: "Who is your craziest/most interesting relative?",
        category: "iceBreaker"
      },
      {
        id: 8,
        qst: "What’s your strangest talent?",
        category: "iceBreaker"
      },
      {
        id: 9,
        qst: "What’s the craziest thing on your bucket list?",
        category: "iceBreaker"
      },
      {
        id: 10,
        qst: "Who is your celebrity look-alike?",
        category: "iceBreaker"
      }
    ]
  };
}

export default {
  data: () => {
    return initialState();
  },
  filters: {
    filteredQuestion: function(data) {
      const number = Math.floor(Math.random() * 9) + 1;
      const tempData = [];
      for (let qst in data) {
        if (+data[qst].id === +number) {
          tempData.push(data[qst]);
        }
      }
      return tempData;
    }
  }
};
</script>
