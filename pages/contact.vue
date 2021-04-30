<template>
  <div class="container">
    <section class="section">
      <h1 class="title has-text-centered">Contact Me</h1>
      <h2 class="subtitle has-text-centered">
        Just let me know if you have any questions.
      </h2>
    </section>
    <div class="columns is-desktop is-centered vcentered">
      <div class="column is-half box pt-5">
        <form
          name="contact-form"
          action="/"
          netlify-honeypot="bot-field"
          method="post"
          netlify
        >
          <input type="hidden" name="form-name" value="contact-form" />
          <p class="hidden">
            <label>Don’t fill this out: <input name="bot-field"/></label>
          </p>
          <b-field label="Name:">
            <b-input placeholder="Name" icon="account" name="name" required>
            </b-input>
          </b-field>

          <b-field label="Email:">
            <b-input
              placeholder="Email"
              type="email"
              icon="email"
              name="email"
              required
            >
            </b-input>
          </b-field>

          <b-field label="Subject:">
            <b-input placeholder="Subject" icon="label" name="subject" required>
            </b-input>
          </b-field>

          <b-field label="Message:">
            <b-input type="textarea" name="message" required></b-input>
          </b-field>

          <b-field class="field is-grouped is-grouped-centered">
            <p class="control">
              <button class="button is-dark" type="submit">Submit</button>
            </p>
          </b-field>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.hidden {
  visibility: hidden;
}
</style>
