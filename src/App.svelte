<script>
  import Header from './UI/Header.svelte'
  import MeetupItem from './Meetups/MeetupItem.svelte'

  const meetups = [
    {
      id: 'm1',
      title: 'Coding Bootcamp',
      subtitle: 'Learn to code in 2 hours',
      description: 'In this meetup we will have some experts that teach you how to code!',
      imageUrl: 'https://picsum.photos/seed/m1/600/300',
      address: '27th  Nerd Road, 32523 New York',
      contactEmail: 'code@test.com'
    },
    {
      id: 'm2',
      title: 'Swim Together',
      subtitle: 'Let\'go for some swimming',
      description: 'We will simply swim some rounds!',
      imageUrl: 'https://picsum.photos/seed/m2/600/300',
      address: '27th  Nerd Road, 32523 New York',
      contactEmail: 'swim@test.com'
    }
  ]
</script>

<style>
  #meetups {
    margin-top: 5rem;
  }
</style>

<Header />

<section id="meetups">
  {#each meetups as meetup}
    <MeetupItem 
      title="{meetup.title}"
      subtitle="{meetup.subtitle}"
      description="{meetup.description}"
      imageUrl="{meetup.imageUrl}"
      address="{meetup.address}"
      contactEmail="{meetup.contactEmail}"
    />
  {/each}
</section>
