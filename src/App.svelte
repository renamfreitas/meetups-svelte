<script>
  import Header from './UI/Header.svelte'
  import MeetupGrid from './Meetups/MeetupGrid.svelte'
  import TextInput from './UI/TextInput.svelte'
  import Button from './UI/Button.svelte'

  let title = ''
  let subtitle = ''
  let address = ''
  let email = ''
  let description = ''
  let imageUrl = ''

  let meetups = [
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

  function addMeetup() {
    const newMeetup = {
      id: Math.random().toString(),
      title: title,
      subtitle: subtitle,
      description: description,
      imageUrl: `https://picsum.photos/seed/${imageUrl}/600/300`,
      address: address,
      contactEmail: email
    }

    meetups = [newMeetup, ...meetups]
  }
</script>

<style>
  main {
    margin-top: 5rem;
  }

  form {
    width: 30rem;
    max-width: 90%;
    margin: auto;
  }

</style>

<Header />

<main>
  <form on:submit|preventDefault="{addMeetup}">
    <TextInput 
      id="title"
      label="Title"
      type="text"
      value={title} 
      on:input={event => (title = event.target.value)}
    />
    <TextInput 
      id="subtitle"
      label="Subitle"
      type="text"
      value={subtitle} 
      on:input={event => (subtitle = event.target.value)}
    />
    <TextInput 
      id="address"
      label="Address"
      type="text"
      value={address} 
      on:input={event => (address = event.target.value)}
    />
    <TextInput 
      id="imageUrl"
      label="Image"
      type="text"
      value={imageUrl} 
      on:input={event => (imageUrl = event.target.value)}
    />
    <TextInput 
      id="email"
      label="E-mail"
      type="email"
      value={email} 
      on:input={event => (email = event.target.value)}
    />
    <TextInput 
      id="description"
      label="Description"
      controlType="textarea"
      value={description} 
      on:input={event => (description = event.target.value)}
    />
    <Button type="submit" caption="save" />
  </form>
  
  <MeetupGrid {meetups} />
</main>


