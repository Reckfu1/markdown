<template>
    <div id="editor">
        <textarea id="text" v-model="mes"></textarea>
        <div class="preview" v-html="previewText"></div>
    </div>
</template>

<script>
import marked from '../../node_modules/marked/marked.min.js'
let mes =
    `A First Level Header
====================
A Second Level Header
---------------------

Now is the time for all good men to come to
the aid of their country. This is just a
regular paragraph.

The quick brown fox jumped over the lazy
dog's back.
### Header 3

> This is a blockquote.
> 
> This is the second paragraph in the blockquote.
>
> ## This is an H2 in a blockquote
Some of these words *are emphasized*.
Some of these words _are emphasized also_.
Use two asterisks for **strong emphasis**.
Or, if you prefer, __use two underscores instead__.
### List:
1. Red
2. Green
3. Blue
>
I get 10 times more traffic from [Google][1] than from
[Yahoo][2] or [MSN][3].

[1]: http://google.com/ "Google"
[2]: http://search.yahoo.com/ "Yahoo Search"
[3]: http://search.msn.com/ "MSN Search"
`
marked.setOptions({
    renderer: new marked.Renderer(),
    gfm: true,
    tables: true,
    breaks: false,
    pedantic: false,
    sanitize: true,
    smartLists: true,
    smartypants: false
});
export default {
    data(){
        return {
            mes
        }
    },
    computed:{
        previewText(){
            return marked(this.mes)
        }
    }
};
</script>

<style lang="css" scoped>
#editor{
    height: 520px;
    width:900px;
    margin:20px auto;
    position: relative;
    box-shadow: 0 0 30px rgba(0,0,0,.3);
}
#text{
    height: 515px;
    width:447px;
    position: absolute;
    left: 0;
    top:0;
    overflow: auto;
    outline: none;
    resize: none;
    font-size: 16px;
}
.preview{
    height: 519px;
    width: 447px;
    position: absolute;
    right:0;
    top:0;
    border:1px solid rgba(0,0,0,.4);
    border-left:none;
    text-align: left;
    text-indent: 10px;
    overflow: auto;
}
</style>