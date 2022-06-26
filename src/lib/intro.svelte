<script>

    const introTextArray = [
        'Hello!',
        'I am Tirthya Kamal Dasgupta.',
        'Welcome to my portfolio.'
    ];

    let introText = '';

    let introTextArrayIndex = 0;
    let introTextArrayInnerIndex = 0;
    const introTextArrayLastTextIndex = introTextArray.length - 1;
    const introTextArrayLastTextLastCharacterIndex = introTextArray[introTextArrayLastTextIndex].length - 1;

    const setText = setInterval(() => {
        if (introText.slice(-1) === '|') {
            introText = introText.slice(0, -1);
        }

        if ((introTextArrayIndex === introTextArrayLastTextIndex) && (introTextArrayInnerIndex === introTextArrayLastTextLastCharacterIndex)) {
            introText += introTextArray[introTextArrayIndex][introTextArrayInnerIndex];

            clearInterval(setText);
        } 
        
        else if (introTextArrayInnerIndex === introTextArray[introTextArrayIndex].length - 1) {
            introText += introTextArray[introTextArrayIndex][introTextArrayInnerIndex] + ' |';

            introTextArrayInnerIndex = 0;
            introTextArrayIndex++;
        }

        else {
            introText += introTextArray[introTextArrayIndex][introTextArrayInnerIndex] + '|';
            
            introTextArrayInnerIndex++;
        }
    }, 50);

</script>

<div class="container">
    <center>
        <h1>{ introText }</h1>
    </center>
</div>

<style>
    .container {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100vh;
    }

    h1 {
        color: #FFFFFF;
        font-family: 'Source Code Pro', monospace;
    }
</style>