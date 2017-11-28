<template>
  <div>
     <div id="example">
     <p>Original message: "{{ message }}"</p>
     <p>Computed reversed message: "{{ reversedMessage }}"</p>
</div>
  </div>
</template>
<script>
export default {
  name: "",
  data: {
    message: 'Hello',
    firstName: 'Foo',
    lastName: 'Bar'
  },
  computed: {
    // 计算属性的 getter
    reversedMessage: function () {
      return this.message.split('').reverse().join('')
    },
    fullName: function () {
      return this.firstName + ' ' + this.lastName
    },
    fullName2: {
    // getter
    get: function () {
      return this.firstName + ' ' + this.lastName
    },
    // setter
    set: function (newValue) {
      var names = newValue.split(' ')
      this.firstName = names[0]
      this.lastName = names[names.length - 1]
    }
  }
  },
  methods: {
    changeFullName: function() {
        // 运行 this.fullName2 = 'John Doe' 时，setter 会被调用，vm.firstName 和 vm.lastName 也会相应地被更新。
        this.fullName2 = 'John Doe'
    }
  }
};
</script>
