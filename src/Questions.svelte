<script lang="ts">
  import Question from './Question.svelte'
  import Results from './Results.svelte'

  let questions: Array<{ text: string; imgSrc: string }> = [
    {
      text:
        'Do you sometimes feel embarrassed when you meet new people because you struggle to hear?',
      imgSrc:
        'https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/q1_topimage.jpg',
    },
    {
      text:
        'Do you feel frustrated when talking to members of your family because you have difficulty hearing them?',
      imgSrc:
        'https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/q2_topimage.jpg',
    },
    {
      text:
        'Do you have difficulty hearing or understanding<br />co-workers, clients, or customers?',
      imgSrc:
        'https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/q3_topimage.jpg',
    },
    {
      text: 'Do you feel restricted or limited by a hearing problem?',
      imgSrc:
        'https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/q4_topimage.jpg',
    },
    {
      text:
        'Do you have difficulty hearing when visiting friends, relatives, or neighbors?',
      imgSrc:
        'https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/q5_topimage.jpg',
    },
    {
      text:
        'Do you have<br />trouble hearing<br />in the movies<br />or in the theater?',
      imgSrc:
        'https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/q6_topimage.jpg',
    },
    {
      text: 'Does a hearing problem cause you to argue with family members?',
      imgSrc:
        'https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/q7_topimage.jpg',
    },
    {
      text:
        'Do you have trouble<br />hearing the TV or<br />radio at levels that<br />are loud enough<br />for others?',
      imgSrc:
        'https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/q8_topimage.jpg',
    },
    {
      text:
        'Do you feel that<br />any difficulty with<br />your hearing limits<br />your personal or<br />social life?',
      imgSrc:
        'https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/q9_topimage.jpg',
    },
    {
      text:
        'Do you have trouble<br />hearing family or<br />friends when you<br />are together<br />in a restaurant?',
      imgSrc:
        'https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/q10_topimage.jpg',
    },
  ]

  let answers: Array<'Yes' | 'No'> = []
</script>

<div class="questions" id="questions">
  {#if answers.length < questions.length}
    <Question
      {...questions[answers.length]}
      number={answers.length + 1}
      of={questions.length}
      on:answer={({ detail }) => (answers = [...answers, detail])}
    />
  {:else}
    <Results
      yesAnswerCount={answers.filter((a) => a === 'Yes').length}
      on:resetQuiz={() => (answers = [])}
    />
  {/if}
</div>
