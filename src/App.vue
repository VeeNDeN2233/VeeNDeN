<template>
  <div class="page">
    <Modal
      v-show="isShowModal"
      :show="isShowModal"
      :scrollable="true"
      header-id="modalHeader"
      body-id="modalBody"
      @close="toggleModal"
    >
    </Modal>

    <Menu> </Menu>

    <div class="footerWindow">
      <button @click="toggleModal">Open Modal</button>
    </div>

    <div
      id="box"
      style="width: 50px; height: 50px; background-color: red"
    ></div>
  </div>
</template>


<script>
import $ from "jquery";
import Modal from "./components/Modal";
import Continue from "./components/Continue";
import Menu from "./components/Menu";
export default {
  components: {
    Modal,
    Continue,
    Menu,
  },
  data: () => ({
    isShowModal: false,
  }),
  methods: {
    toggleModal() {
      this.isShowModal = !this.isShowModal;
    },
  },
};

// ТЕРМИНАЛ // // // // // // // // // // / / / / / /
$(function () {
  $(".terminal").on("click", function () {
    $("#input").focus();
  });

  $("#input").on("keydown", function search(e) {
    if (e.keyCode == 13) {
      // append your output to the history,
      // here I just append the input
      $("#history").append($(this).val() + "<br/>");

      // you can change the path if you want
      // crappy implementation here, but you get the idea
      if ($(this).val().substring(0, 3) === "cd ") {
        $("#path").html($(this).val().substring(3) + "&nbsp;>&nbsp;");
      }

      // clear the input
      $("#input").val("");
    }
  });
});

// // // // // // // // // // // //

$(document).ready(function () {
  $(".run").click(function () {
    $("#box")
      .animate({ opacity: "0.1", left: "+=400" }, 1200)
      .animate(
        { opacity: "0.4", top: "+=160", height: "20", width: "20" },
        "slow"
      )
      .animate({ opacity: "1", left: "0", height: "100", width: "100" }, "slow")
      .animate({ top: "0" }, "fast")
      .slideUp()
      .slideDown("slow");
    return false;
  });
});
</script>


<style>
.consol {
  display: flex;
  flex-direction: column;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Source Sans Pro", sans-serif;
  margin: 0;
  padding: 0;
  height: 100vh;
}

.page {
  width: 100%;
  min-height: 100%;
  display: flex;
  flex-direction: row;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background: rgb(2, 0, 36);
  background-size: cover;
  background: linear-gradient(
    90deg,
    rgba(2, 0, 36, 1) 0%,
    rgba(9, 9, 121, 1) 0%,
    rgba(0, 212, 255, 1) 100%
  );
}

html,
body {
  height: 100%;
  margin: 0;
  padding: 0;
}

.originWindow {
  width: 35%;
  order: 1;
  background-color: black;
  position: relative;
}

.headerWindow {
  width: 100%;
  height: 30px;
  background-color: azure;
  display: flex;
  justify-content: flex-end;
}

.halloText {
  margin: 30px;
  color: azure;
  opacity: 75%;
  text-align: center;
}

.btnWindowExit {
  height: 30px;
  width: 30px;
  background-color: red;
  border-radius: 0%;
  border: 0px solid;
}

.footerWindow {
  /* position: absolute; */
  bottom: 0;
  right: 0;
}

body {
  background-color: #ececec;
  background: linear-gradient(135deg, #0f55e4, #0a3a9c);
  color: #fff;
  /*padding: 0.5em 1em;*/
  -webkit-font-smoothing: antialiased;
}

.terminal {
  background: black;
  color: white;
  font: courier;
  padding: 10px;
  height: 100px;
  overflow: scroll;
}

.line {
  display: table;
  width: 100%;
}

.terminal span {
  display: table-cell;
  width: 1px;
}

.terminal input {
  display: table-cell;
  width: 100%;
  border: none;
  background: black;
  color: white;
  outline: none;
}
</style>





