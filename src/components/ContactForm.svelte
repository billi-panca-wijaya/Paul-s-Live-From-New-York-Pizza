<script>
  let formData = {
    name: "",
    phone: "",
    email: "",
    date: "",
    guests: "2 People",
    message: "",
  };

  let submitted = false;
  let submitting = false;

  async function handleSubmit() {
    submitting = true;

    // Simulate form submission
    await new Promise((resolve) => setTimeout(resolve, 1000));

    submitted = true;
    submitting = false;

    // Reset form after delay
    setTimeout(() => {
      submitted = false;
      formData = {
        name: "",
        phone: "",
        email: "",
        date: "",
        guests: "2 People",
        message: "",
      };
    }, 3000);
  }
</script>

<div class="contact-form-container">
  <h3 class="form-title">Reservations & Contact</h3>
  <p class="form-subtitle">Book a table or send us a message.</p>

  {#if submitted}
    <div class="success-message">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="48"
        height="48"
        viewBox="0 0 24 24"
        fill="none"
        stroke="currentColor"
        stroke-width="2"
      >
        <path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"></path>
        <polyline points="22 4 12 14.01 9 11.01"></polyline>
      </svg>
      <p>Thank you! Your request has been received.</p>
    </div>
  {:else}
    <form on:submit|preventDefault={handleSubmit} class="form">
      <div class="form-row">
        <div class="form-group">
          <label for="name" class="form-label">Name</label>
          <input
            type="text"
            id="name"
            bind:value={formData.name}
            placeholder="Your Name"
            required
            class="form-input"
          />
        </div>
        <div class="form-group">
          <label for="phone" class="form-label">Phone</label>
          <input
            type="tel"
            id="phone"
            bind:value={formData.phone}
            placeholder="(555) 123-4567"
            required
            class="form-input"
          />
        </div>
      </div>

      <div class="form-group">
        <label for="email" class="form-label">Email</label>
        <input
          type="email"
          id="email"
          bind:value={formData.email}
          placeholder="you@example.com"
          required
          class="form-input"
        />
      </div>

      <div class="form-row">
        <div class="form-group">
          <label for="date" class="form-label">Date</label>
          <input
            type="date"
            id="date"
            bind:value={formData.date}
            class="form-input"
          />
        </div>
        <div class="form-group">
          <label for="guests" class="form-label">Guests</label>
          <select id="guests" bind:value={formData.guests} class="form-input">
            <option>2 People</option>
            <option>3 People</option>
            <option>4 People</option>
            <option>5+ People</option>
          </select>
        </div>
      </div>

      <div class="form-group">
        <label for="message" class="form-label">Message (Optional)</label>
        <textarea
          id="message"
          bind:value={formData.message}
          rows="3"
          class="form-input form-textarea"
        ></textarea>
      </div>

      <button type="submit" class="submit-btn" disabled={submitting}>
        {#if submitting}
          Sending...
        {:else}
          Send Request
        {/if}
      </button>
    </form>
  {/if}
</div>

<style>
  .contact-form-container {
    background-color: var(--color-gray-100);
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    border: 1px solid var(--color-gray-200);
  }

  .form-title {
    font-family: var(--font-heading);
    font-size: 1.75rem;
    font-weight: 700;
    color: var(--color-pizza-dark);
    margin-bottom: 0.5rem;
  }

  .form-subtitle {
    color: var(--color-gray-500);
    font-size: 0.875rem;
    margin-bottom: 1.5rem;
  }

  .form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .form-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }

  @media (max-width: 640px) {
    .form-row {
      grid-template-columns: 1fr;
    }
  }

  .form-group {
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
  }

  .form-label {
    font-size: 0.875rem;
    font-weight: 700;
    color: var(--color-gray-700);
  }

  .form-input {
    padding: 0.625rem 0.75rem;
    border: 1px solid var(--color-gray-300);
    border-radius: 4px;
    font-family: var(--font-body);
    font-size: 1rem;
    transition: border-color 0.15s ease;
    background-color: white;
  }

  .form-input:focus {
    outline: none;
    border-color: var(--color-pizza-red);
  }

  .form-textarea {
    resize: vertical;
    min-height: 80px;
  }

  .submit-btn {
    background-color: var(--color-pizza-red);
    color: white;
    padding: 0.875rem;
    border: none;
    border-radius: 4px;
    font-family: var(--font-heading);
    font-size: 1rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    cursor: pointer;
    transition: background-color 0.15s ease;
  }

  .submit-btn:hover:not(:disabled) {
    background-color: #b71c1c;
  }

  .submit-btn:disabled {
    opacity: 0.7;
    cursor: not-allowed;
  }

  .success-message {
    text-align: center;
    padding: 2rem;
    color: #059669;
  }

  .success-message svg {
    margin-bottom: 1rem;
  }

  .success-message p {
    font-size: 1.125rem;
    font-weight: 600;
  }
</style>
