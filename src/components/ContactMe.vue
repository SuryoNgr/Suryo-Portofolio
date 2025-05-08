<template>
    <section id="contact" class="contact-me bg-gray-900 text-white py-12">
      <div class="container mx-auto px-4 max-w-2xl">
        <h2 class="text-4xl font-bold text-center mb-6">📫 Contact Me</h2>
        <p class="text-center text-gray-300 mb-10">
          Silakan hubungi saya melalui formulir di bawah ini, dan saya akan segera membalas pesan Anda.
        </p>
  
        <form @submit.prevent="submitForm" class="bg-gray-800 p-6 rounded-xl shadow-md space-y-5">
          <input type="hidden" name="_subject" value="Pesan dari Portfolio" />
  
          <div>
            <label class="block mb-1 text-gray-200">Nama</label>
            <input
              v-model="form.name"
              name="name"
              required
              class="w-full px-4 py-2 rounded bg-gray-700 text-white border border-gray-600"
            />
          </div>
  
          <div>
            <label class="block mb-1 text-gray-200">Email</label>
            <input
              type="email"
              v-model="form.email"
              name="email"
              required
              class="w-full px-4 py-2 rounded bg-gray-700 text-white border border-gray-600"
            />
          </div>
  
          <div>
            <label class="block mb-1 text-gray-200">Pesan</label>
            <textarea
              v-model="form.message"
              name="message"
              required
              rows="5"
              class="w-full px-4 py-2 rounded bg-gray-700 text-white border border-gray-600"
            ></textarea>
          </div>
  
          <button
            type="submit"
            class="bg-indigo-600 hover:bg-indigo-700 text-white font-semibold px-6 py-2 rounded-lg transition duration-300"
          >
            Kirim Pesan
          </button>
  
          <!-- Pesan status -->
          <p v-if="success" class="text-green-400 text-center mt-4">Pesan berhasil dikirim!</p>
          <p v-if="error" class="text-red-400 text-center mt-4">Gagal mengirim pesan. Coba lagi ya.</p>
        </form>
  
        <div class="text-center mt-8 text-gray-400">
          atau langsung email ke:
          <a href="mailto:suryoo.nug@gmail.com" class="text-indigo-400 hover:underline">suryoo.nug@gmail.com</a>
        </div>
      </div>
    </section>
  </template>
  
  <script>
        export default {
        data() {
            return {
            form: {
                name: "",
                email: "",
                message: ""
            },
            success: false,
            error: false
            };
        },
        methods: {
            async submitForm() {
            this.success = false;
            this.error = false;
            try {
                const response = await fetch("https://formspree.io/f/xanojpqp", {
                method: "POST",
                headers: {
                    "Content-Type": "application/json",
                    Accept: "application/json"
                },
                body: JSON.stringify(this.form)
                });

                const result = await response.json();

                if (response.ok) {
                this.success = true;
                this.resetForm();
                this.hideMessageAfterDelay();
                } else {
                this.error = true;
                this.hideMessageAfterDelay();
                }
            } catch (e) {
                this.error = true;
                this.hideMessageAfterDelay();
            }
            },
            resetForm() {
            this.form.name = "";
            this.form.email = "";
            this.form.message = "";
            },
            hideMessageAfterDelay() {
            setTimeout(() => {
                this.success = false;
                this.error = false;
            }, 3000); 
            }
        }
        };

  </script>
  
  <style scoped>
  .contact-me {
    background: linear-gradient(135deg, #13131d 0%, #14143d 100%);
  }
  </style>
  