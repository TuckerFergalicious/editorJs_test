<template>
  <div class>
    <div class>
      <h1 style="text-align:center">Mood Choice
      </h1>
    </div>
    <button class='colorChoice' style="background-color:yellow;" type="button" name="button" @click="setColor("yellow")">Energized</button>
    <button class='colorChoice' style="background-color:green" type="button" name="button" @click="setColor("green")">Relaxed</button>
    <button class='colorChoice' style="background-color:blue" type="button" name="button" @click="setColor("blue")"></button>
     <div class="editorx_body>
      <div class id="codex-editor"/>
    </div
    <div class="editorx_body">
      <pre>{{color}}</pre>
    </div>
</template>

<script>
import EditorJS from "@editorjs/editorjs";
import Header from "@editorjs/header";
import Paragraph from "@editorjs/paragraph";
import List from "@editorjs/list";
export default {
  data() {
    return {
      value: null,
    };
  },
  methods: {
    save: function () {
      editor.save().then((savedData) => {
        console.log(savedData);
        this.value = savedData;
        //self.handleChange(savedData)
      });
    },
    setColor: function (color) {
      editor.save().then((color) =>  {
      console.log(color)
      if(color == "yellow"){
        this.color == "yellow";
      }
      else if (color == "green"){
        this.color == "green"
      }
      else if (color == "blue"){
        this.color == "blue"
      }
      else{
        this.color == "white"
      }
      document.getElementByClass("editorx_body").style.background = color;
      })
     },
    myEditor: function () {
      window.editor = new EditorJS({
        holder: "codex-editor",
        autofocus: true,
        /**
         * This Tool will be used as default
         */
        initialBlock: "paragraph",
        tools: {
          table: {
            class: Table,
            inlineToolbar: true,
            config: {
              rows: 2,
              cols: 3,
            },
          },
          list: {
            class: List,
          },
          paragraph: {
            class: Paragraph,
            config: {
              placeholder: ".",
            },
          },
        },
        onReady: function () {
          console.log("ready");
        },
        onChange: function () {
          console.log("change");
          // editor.save().then((savedData) => {
          //   //console.log(savedData)
          //   this.value = savedData
          // });
        },
      });
    },
  },
  mounted: function () {
    this.myEditor();
  },
};
</script>

<style lang="css" scoped >
.editorx_body {
  /* width: 62%;
  margin-left: 15%; */
  width: 90%;
  margin-left: 5%;
  border: 2px solid #f1f3f5;
  box-sizing: border-box;
}
.colorChoice {
  position: relative;
  margin-left: 10%;
  width: 20%;
  height: 80px;
}
.ce-block--focused {
  background: linear-gradient(
    90deg,
    rgba(2, 0, 36, 1) 0%,
    rgba(9, 9, 121, 0.5438550420168067) 35%,
    rgba(0, 212, 255, 1) 100%
  );
}
</style>
