<script>
  import Button from '../UI/Button.svelte'

  export let title
  export let subtitle
  export let description
  export let imageUrl
  export let address
  export let contactEmail
</script>

<style lang="scss">
  @import "./MeetupItem.scss";
</style>

<article>
  <header>
    <h1>{title}</h1>
    <h2>{subtitle}</h2>
    <p>{address}</p>
  </header>
  <div class="image">
    <img src="{imageUrl}" alt="{title}">
  </div>
  <div class="content">
    <p>{description}</p>
  </div>
  <footer>
    <Button href="mailto:{contactEmail}" type="button" caption="Contact" />
    <Button mode="outline" type="button" caption="Favorite" />
    <Button type="button" caption="Show Details" />
  </footer>
</article>