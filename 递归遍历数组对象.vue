<template>
  <div></div>
</template>
<script>
export default {
  data() {
    return {
      nameObj: [
        {
          name: "aa",
          like: 111,
          clid: [
            { name: "aa1", like: 111111 },
            { name: "aa2", like: 222222 },
            {
              name: "aa3",
              like: 333333,
              clid: [
                { name: "aaaa1", like: 11111100 },
                { name: "aaaa2", like: 22222200 }
              ]
            }
          ]
        },
        {
          name: "bb",
          like: 111,
          clid: [
            { name: "bb1", like: 111111 },
            { name: "bb2", like: 222222 },
            {
              name: "bb3",
              like: 333333,
              clid: [
                { name: "bbbb1", like: 11111100 },
                { name: "bbbb2", like: 22222200 }
              ]
            }
          ]
        },
        {
          name: "cc",
          like: 111,
          clid: [
            { name: "cc1", like: 111111 },
            { name: "cc2", like: 222222 },
            {
              name: "cc3",
              like: 333333,
              clid: [
                { name: "cccc1", like: 11111100 },
                { name: "cccc2", like: 22222200 }
              ]
            }
          ]
        }
      ]
    };
  },
  mounted() {
    console.log(this.fn1(this.nameObj, []));
  },
  methods: {
    fn1(list, emptylist) {
      list.forEach(item => {
        emptylist.push({ name: item.name, like: item.like });
        if (item.clid) {
          this.fn1(item.clid, emptylist);
        }
      });

      return emptylist;
    }
  }
};
</script>