# CSGO-SKINS-BOT-
a simple way to make gold on the website , full tutorial 



there is a website called csgodouble . com , you can get money from it sigh in with steam press free coints enter " STARTINGMONEY123" and you will get 500 points , but there is another thing to it , there is a bot that makes money there you just need to activate it its completely free , if you join that website and enter "STARTINGMONEY123" contact me here ill send you the bot with the instuctions.
-
-
-
-
-
-
-
After you complete the steps and get the 500 coints just hit ctrl+shift+j and pas the code bellow and hit enter , thats all you have to do and sit and wait leave over night and your coins will rise :)
-
-
-
-
-
-
-
-
-
-
    var initialBetAmount = 1; // the amount you want to start betting with
    var mode = 'martingale'; // can be 'martingale' or 'anti-martingale' (WAT?     https://en.wikipedia.org/wiki/Martingale...ng_system) )
    var betColor = 'red'; // can be 'red' or 'black'
    function tick(){var a=getStatus();if(a!==lastStatus&&"unknown"!==a){switch(a)    {case"waiting":bet();break;case"rolled":rolled()}lastStatus=a,printInfo()}}function checkBalance(){return     getBalance()<currentBetAmount?(console.warn("BANKRUPT! Not enough balance for next bet,     aborting."),clearInterval(refreshIntervalId),!1):!0}function printInfo(){var a=" \nStatus: "+lastStatus+"\nRolls     played: "+currentRollNumber+"\nInitial bet amount: "+initialBetAmount+"\nCurrent bet amount:     "+currentBetAmount+"\nLast roll result: "+(null===wonLastRoll()?"-    ":wonLastRoll()?"won":"lost");console.log(a)}function rolled(){return"anti-martingale"===mode?void     antiMartingale():(martingale(),void currentRollNumber++)}function antiMartingale()    {currentBetAmount=wonLastRoll()?2*currentBetAmount:initialBetAmount}function martingale()    {currentBetAmount=wonLastRoll()?initialBetAmount:2*currentBetAmount}function bet(){checkBalance()&&    (setBetAmount(currentBetAmount),setTimeout(placeBet,50))}function setBetAmount(a)    {$betAmountInput.val(a)}function placeBet(){return"red"===betColor?    ($redButton.click(),void(lastBetColor="red")):($blackButton.click(),void(lastBetColor="black"))}function     getStatus(){var a=$statusBar.text();if(hasSubString(a,"Rolling     in"))return"waiting";if(hasSubString(a,"***ROLLING***"))return"rolling ";if(hasSubString(a,"rolled")){var     b=parseInt(a.split("rolled")[1]);return lastRollColor=getColor(b),"rolled"}return"unknown"}function getBalance()    {return parseInt($balance.text())}function hasSubString(a,b){return a.indexOf(b)>-1}function getColor(a)    {return 0==a?"green":a>=1&&7>=a?"red":"black"}function wonLastRoll(){return lastBetColor?    lastRollColor===lastBetColor:null}var     currentBetAmount=initialBetAmount,currentRollNumber=1,lastStatus,lastBetColor,lastRollColor,$balance=$("#bal    ance"),$betAmountInput=$("#betAmount"),$statusBar=$(".progress #banner"),$redButton=$("#panel1-7     .betButton"),$blackButton=$("#panel8-14 .betButton"),refreshIntervalId=setInterval(tick,500);
