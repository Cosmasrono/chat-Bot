<template>
  <div class=" bg-slate-800 text-white items-center justify-center flex flex-col">
    <div class=" ">
      <h1 class=" text-3xl text-red-600 p-4 m-4">STUDENT INQUIRY CHATBOT</h1>
      <p class=" italic">Hi, welcome I am an inquiry chatbot! Go ahead and send me a message. 😄<br>
        Please note I answer specific questions. 🤨
      </p>
    </div>
    <div class="">
      <h1 class=" text-green-500">Hint</h1>
      <p class=" ">ask question eg. Hi,hello,good morning</p>
    </div>

    <div class="all">
      <div class="chatbot">
        <div class=" text-4xl p-3 m-3">
          <h2>Chat with me</h2>
        </div>
        
          <div class="chatbot-message" v-html="chatbotDialogHTML"></div>
      
        <div class="chatbot-footer gap-24">
          <input type="text" ref="chatbotText" placeholder="Type your message here..." class=" text-black p-3 rounded-md">
          <button @click="handleUserInput" class=" bg-blue-700 p-3 m-2 rounded-md">Send</button>
        </div>
      <!--   <div id="chatbot-input">
          <input type="text" ref="chatbotText" placeholder="Ask me a question..."><br><br>
 -->
          <!-- <button @click="handleUserInput">Submit</button> -->
          <button @click="clear" class="  bg-blue-700 p-3 m-2 rounded-md">Clear</button>
        </div>

      </div>
    </div>

</template>

<script>
export default {
  data() {
    return {
      chatbotDialogHTML: "",
      responses: {
      "hi": "hi hello there",
      "hello":"Hello, how may i help you today?",
      "hey":"Hello, how can i assit you today?",
      "good morning":"Good morning to you how may i assit you today?",
      "morning":"Good morning to you how may i assit you today?",
      "good evening":"  Good evening too how may i assit you today?",
      "evening":"  Good evening too how may i assit you today?",
      "good afternoon":"Good afternoon how may i assit you today?",
      "afternoon":"Good afternoon how may i assit you today?",
      "how are you":"As a language model, I do not have emotions,\n but I am functioning properly and am ready to assist you with any academic questions you may have.\n How can I assist you today?",
      "school fees": "kindly visit kabarak student finance with your student ID for further assistance",
      "school elections": "kabarak school elections are held annually, \n the current school president is Karen ",
      "attachment": "PRE ATTACHMENT and POST ATTACHMENT",
      "pre attachment":"This is only available for third year second semester students",
      "post attachment":"This is only available for fourth year second semester students",
      "missing marks": "Kindly visit school of business SAA secretary office ,\n get a missing marks form , \n fill the missing units and consult the secetrary for further assitances",
      "incomplete marks": "This means that you are either missing the exam or cat marks, \n visit the SAA for further assistance",
      "exam card":"Your exam card is only available  when you have cleared the school fee,\n you can then collect it from the school of business department",
      "retake":"When you haven't met the  40% academic exam requirements you are required to re-register the unit again ",
      "attachment letters":"The letters are issued when one has attained the correct academic score(i.e one retake,two missing marks) pick the letters from your respective school departments",
      "lectures contacts":"",
      "attachment assessment":"The assessment is done when the required duration is done where by  minimum duration is 2 months",
      "transcript":"you can download it from your student's portal or you can ask the SAA  to help you print it",
      "collection of certificate":"once you have completed your academic journey and graduated, you are required to come and collect your academic transcript from the admission's office",
      "course registration":"NORMAL REGISTRATION,SPECIAL EXAMS ,RETAKE REGISTRATION,SUPPLEMENTARY EXAM",
      "normal":"when you have cleared the previous semester school fees ",
      "normal registration":"when you have cleared the previous semester school fees ",
      "special exam":"when you had missed some exams with valid reasons the school is obliged to give you the exams.For further guidance you can contact the school SAA through <strong>+254712312312</strong> ",
      "special":"when you had missed some exams with valid reasons the school is obliged to give you the exams.For further guidance you can contact the school SAA through <strong>+254712312312</strong> ",
      "retake registration":"You are advised to visit your student's portal ,course registration section select retake option and register the unit you are retaking",
      "supplementary exam":"This is offered only to students who are on their final year who are yet to graduate,incase they got a retake",
      "supplementary":"This is offered only to students who are on their final year who are yet to graduate,incase they got a retake",
      "graduation":"Those who have achieved the university academic requirements are allowed to graduate",
      "graduation gowns":"the school will send a memo to your school email,explaining all the details,when and where to pick the gowns",
      "graduation certificate":"once you have completed your academic journey and graduated, you are required to come and collect your academic transcript from the admission's office",
      "timetable":"EXAMS OR CLASS TIMETABLE",
      "exam timetable":"a draft timetable is usually released a month before and the final timetable is released days to exams",
      "class timetable":"This is released a week before opening of the next semester",
      "exam collision":"You are advised to visit the school timetabling office for further assistance",
      "timetable collision":"You are advised to visit the school timetabling office for further assistance",
      "lectures phone number":"",
      "saa contact":" +25478345665",
      "saa phone number":"+25478345665",
      "exam qualification":"when you have paid full school fees and attained 80% class attendance",
      "clearance form":"pick the forms from the admission office"
      }
    };
  },
  methods: {
    handleUserInput() {
      let userInput = this.$refs.chatbotText.value.toLowerCase();
      this.chatbotDialogHTML += `<div class="chatbot-message-user">${userInput}</div>`;
      this.$refs.chatbotText.value = "";
      this.chatbotDialogHTML += `<div class="chatbot-message-bot">${this.responses[userInput] || "Sorry, I don't understand that yet. 😅"}</div>`;
    },

      

    clear() {
      this.chatbotDialogHTML = "";
    },

  }
};
</script>
