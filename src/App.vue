<template>
 <div id="app">
  <div id="content">
    <file-header></file-header>
    <contract-page></contract-page>
  </div>
  
</div>
<div id="print">
      <button id="btnprint" @click="makePDF"> Convert to PDF</button>
  </div>
</template>

<script>
import FileHeader from './components/FileHeader'
import ContractPage from './components/ContractPage'
import jsPDF from "jspdf";
import html2canvas from "html2canvas";


export default {
  name: 'App',
  components: {
   FileHeader,
   ContractPage
  },
  methods: {
    makePDF(){
     
      var dom = document.getElementById("app");
     
      html2canvas(dom, {
         allowTaint: true,
        scrollY: 0,
        scrollX: 0,
        Usecors: true, 
        width: 3000,
        height: dom.offsetHeight
      }).then((canvas) => {
        var contentWidth = canvas.width;
        var contentHeight = canvas.height;
        var pdfWidth = (contentWidth + 10) / 2 * 0.75;
        var pdfHeight = (contentHeight + 200) / 2 * 0.75; //  500 is left blank at the bottom
        var imgWidth = pdfWidth;
        var imgHeight = contentHeight / 2 * 0.75; // There is no need to leave a blank distance here
        var pageData = canvas.toDataURL("image/jpeg", 1.0);
        var pdf = new jsPDF("", "px", [pdfWidth, pdfHeight]);
        pdf.addImage(pageData, "jpeg", 0, 0, imgWidth, imgHeight);
        pdf.save( "cn.pdf");
      })



      
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: black;
  line-height: 1.6;
}
#content {
 border:1px solid black;
 margin: 50px;
 padding: 50px;
}
#btnprint{
  background-color: black; 
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
#print{
  margin: 50px;
  padding: 50px;
}
.html2canvas-container { 
    width: 3000px; 
    height: 3000px; 
}

</style>
