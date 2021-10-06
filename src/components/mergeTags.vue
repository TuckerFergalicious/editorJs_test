<template>
  <div class>
    <div class>
      <h1 style="text-align:center">Merge Tags
      </h1>
    </div>
     <div class="editorx_body">
      <div class id="codex-editor"/>
      <div class id="tag_opt"/>
      <div class id="tag_opt2"/>
    </div
    <div class="editorx_body">
      <pre>{{value}}</pre>
    </div>
</template>

<script>
import EditorJS from "@editorjs/editorjs";
import Header from "@editorjs/header";
import Paragraph from "@editorjs/paragraph";
import List from "@editorjs/list";
import Checklist from "@editorjs/checklist";
import Table from "@editorjs/checklist";
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
    tags: function () {
      editor.save().then((savedData) => {
        console.log(savedData);
        this.value = savedData;
        tag_content: "tag-editor"
        //self.handleChange(savedData)
      });
    myEditor: function () {
      window.editor = new EditorJS({
        holder: "codex-editor",
        autofocus: true,
        /**
         * This Tool will be used as default
         */
        initialBlock: "paragraph",
        tools: {
          header: {
            class: Header,
            config: {
              placeholder: 'Subject',
              levels: [2, 3, 4],
              defaultLevel: 3,
            }
          },
          table: {
            class: Table,
            inlineToolbar: true,
          },
          tableChoice: {
            class: Checklist,
            inlineToolbar: true,
          },
          checklist: {
            class: Checklist,
            inlineToolbar: true,
          },
          paragraph: {
            class: Paragraph,
            config: {
              placeholder: "Tag Content.",
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
.tag_opt {
  /* width: 62%;
  margin-left: 15%; */
  width: 20%;
  margin-top:10%;
  margin-left: 20%;
  border: 2px solid #f1f3f5;
  box-sizing: border-box;
}

.tag_opt2 {
  /* width: 62%;
  margin-left: 15%; */
  width: 20%;
  margin-top:10%;
  margin-left: 60%;
  border: 2px solid #f1f3f5;
  box-sizing: border-box;
}
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
