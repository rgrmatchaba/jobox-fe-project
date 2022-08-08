<template>

<div>
    <h2>
        FIXED TERM AGREEMENT
    </h2>
    <p> between </p>
    <div id="title">
      <h2>BMF ATTORNEYS </h2>
      <h2>with company registration number 2022/123456/07</h2>
    </div>
     <p> and </p>
     <div id="title">
       <input v-model="this.clientName" placeholder="Client Name" type="text" size="80"/>
     </div>
     <p> Collectively referred herein as the “parties” </p>

<ol>
  <li> <span style="font-size:17.5px; font-weight: bold;">Payment Terms:</span>   
    <ul style="list-style-type: disc;">BMF Attorney’s fee  <input v-model="this.insertPaymentAmount" placeholder="Payment Amount" type="text"/> (excluding VAT). 
        The retainer fee can be paid upfront, or month-to-month and the payment terms can be payable as 
        follows:

            <ul>Upfront:
                <ul style=" list-style-type: square;"> Three-twelfths of the fee during the probation period in 3 equal instalments by the 7th day of each month</ul>
                <ul style=" list-style-type: square;"> Nine-twelfths of the fee upon conclusion of the probation period of employment payable on the 7th day of the 4th month. </ul>
            </ul>

            <ul >Month-to-month:
                <ul style=" list-style-type: square;"> The month-to-month fee shall be paid by the 7th day of each month</ul>           
            </ul>
    </ul>

    <ul style="list-style-type: disc;">
      No variation or amendment to this Agreement shall be of any effect unless such amendment is put in writing and signed by all parties
    </ul>

    <ul style="list-style-type: disc;">
      Any documentation prepared by <span style="font-weight: bold;">BMF Attorneys</span> remains its property
    </ul>
  </li>

  <br/>

  <li> <span style="font-size:17.5px; font-weight: bold;">Appointment:</span> 
    <ol>
      <li>
        The Client has procured the services of <span style="font-weight: bold;">BMF Attorneys</span>  and hereby accepts the appointment as an independent contractor of the Client for a fixed period of time.
      </li>
      <li>
        The reason for this fixed-term contract is <span style="font-weight: bold;"> for the appointment and completion of the
        <input v-model="this.serviceDescription" placeholder="Service Description" type="text" size="150" /> </span>
      </li>
    </ol>  
  </li>
  <br/>

  <li>  <span id="text">Duration:</span>  
    <ol>
      <li>
        Notwithstanding the date of signature hereof, this fixed term contract shall be deemed to have 
        commenced on the <input type="date" id="startDate" name="startDate" placeholder="Start Date"/> and will terminate, without further notice, on the <input type="date" id="endDate" name="endDate" placeholder="End Date"/>. 
      </li>
      <li>
        The automatic termination of the contract on the Termination Date shall not be construed as a dismissal but as the completion of a fixed term contract.
      </li>   
    </ol>
  </li>
</ol>

<div>
  <p> Signed at</p>
   <p> on </p>
   <br/>
   <div id="line"></div>
   <p> Who warrants authority on behalf of Jobox</p>
   <br/>
   <p> Signed at</p>
   <p> on </p>
   <br/>
   <div id="line"></div>
   <p> Who warrants authority on behalf of Jobox</p>

</div>

</div>
</template>

<script>

export default {
  components: {
  
  },
  data() {
    return {
      clientName: "",
      insertPaymentAmount : "",
      serviceDescription: "",
      startDate: "",
      endDate: ""
    }
},
}
</script>

<style>
ul {
  list-style-type: circle;
  display:list-item;
  list-style-position:inside;
}
ol {
  counter-reset: item;
}
li {
  display: block;
  line-height: 1.6;
}
li:before {
  content: counters(item, ".") " ";
  counter-increment: item;
  font-weight: bold;
}
#text{
   font-weight: bold;
   font-size:17.5px; 
}
#title {
  text-align: center;
}
input[type=text] {
  border: none;
  background-color: transparent;
  resize: none;
  outline: none;
  font-size:15px;
}
input[type=date] {
  border: none;
  background-color: transparent;
  resize: none;
  outline: none;
  font-size:15px;
}
#line{
  width:60vw;
  border:1px solid black;
}
input::placeholder {
  text-align: center;
}
input:placeholder-shown {
  text-align: center;
}
</style>