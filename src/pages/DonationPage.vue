<template>
  <q-page-container class="donation-page">
    <NavBar />
<<<<<<< HEAD
    
    <div class="donation-container">
      <HeroSection 
        title="Support Our Mission" 
        subtitle="Your donation helps us reunite more families and find missing loved ones" 
=======

    <div class="donation-container">
      <HeroSection
        title="Support Our Mission"
        subtitle="Your donation helps us reunite more families and find missing loved ones"
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
      />

      <div class="donation-form">
        <h2 class="section-title">Choose a donation amount</h2>
<<<<<<< HEAD
        
        <div class="amount-options">
          <div 
            v-for="amount in donationAmounts" 
            :key="amount.value"
            class="amount-option"
            :class="{ 'selected': selectedAmount === amount.value }"
            @click="selectedAmount = amount.value"
          >
            <div class="amount">${{ amount.value }}</div>
=======

        <div class="amount-options">
          <div
            v-for="amount in donationAmounts"
            :key="amount.value"
            class="amount-option"
            :class="{ selected: selectedAmount === amount.value }"
            @click="selectedAmount = amount.value"
          >
            <div class="amount">EGP {{ amount.value }}</div>
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
            <div class="description">{{ amount.description }}</div>
          </div>

          <div class="custom-amount">
            <q-input
              v-model="customAmount"
<<<<<<< HEAD
              label="Enter custom amount"
              prefix="$"
              type="number"
              :rules="[val => val > 0 || 'Please enter a valid amount']"
=======
              :placeholder="`Enter custom amount`"
              type="number"
              :rules="[(val) => val > 0 || 'Please enter a valid amount']"
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
              @update:model-value="selectedAmount = Number(customAmount)"
            />
          </div>
        </div>

        <h2 class="section-title q-mt-xl">Choose a donation frequency</h2>
<<<<<<< HEAD
        
=======

>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
        <div class="frequency-options">
          <q-btn-toggle
            v-model="frequency"
            spread
            no-caps
            rounded
            unelevated
            :options="[
<<<<<<< HEAD
              {label: 'Monthly', value: 'monthly'},
              {label: 'One time', value: 'one-time'}
=======
              { label: 'Monthly', value: 'monthly' },
              { label: 'One time', value: 'one-time' },
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
            ]"
          />
        </div>

        <div class="donation-summary q-mt-lg">
          <p class="text-h6">
<<<<<<< HEAD
            You selected: ${{ selectedAmount }} {{ frequency === 'monthly' ? 'monthly' : 'one-time' }} donation
=======
            You selected: EGP {{ selectedAmount }}
            {{ frequency === 'monthly' ? 'monthly' : 'one-time' }} donation
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
          </p>
        </div>

        <div class="action-buttons">
<<<<<<< HEAD
          <q-btn
            label="Cancel"
            flat
            color="grey"
            class="q-mr-md"
            @click="$router.go(-1)"
          />
=======
          <q-btn label="Cancel" flat color="grey" class="q-mr-md" @click="$router.go(-1)" />
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
          <q-btn
            label="Proceed to Checkout"
            color="primary"
            unelevated
            rounded
            :disable="!selectedAmount"
            @click="proceedToCheckout"
          />
        </div>
      </div>
    </div>

    <FooterComponent />
  </q-page-container>
</template>

<script>
<<<<<<< HEAD
import { ref } from 'vue';
import NavBar from 'src/components/NavBar.vue';
import FooterComponent from 'src/components/Footer.vue';
import HeroSection from 'src/components/HeroSection.vue';
import { useRouter } from 'vue-router';
=======
import { ref } from 'vue'
import NavBar from 'src/components/NavBar.vue'
import FooterComponent from 'src/components/Footer.vue'
import HeroSection from 'src/components/HeroSection.vue'
import { useRouter } from 'vue-router'
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e

export default {
  name: 'DonationPage',
  components: {
    NavBar,
    FooterComponent,
<<<<<<< HEAD
    HeroSection
  },
  setup() {
    const selectedAmount = ref(10);
    const customAmount = ref('');
    const frequency = ref('monthly');
    const router = useRouter();

    const donationAmounts = [
      { 
        value: 10, 
        description: 'Help us maintain our search database and infrastructure' 
      },
      { 
        value: 25, 
        description: 'Support our outreach programs and awareness campaigns' 
      },
      { 
        value: 50, 
        description: 'Enable us to expand our search capabilities and reach' 
      }
    ];
=======
    HeroSection,
  },
  setup() {
    const selectedAmount = ref(10)
    const customAmount = ref('')
    const frequency = ref('monthly')
    const router = useRouter()

    const donationAmounts = [
      {
        value: 10,
        description: 'Help us maintain our search database and infrastructure',
      },
      {
        value: 25,
        description: 'Support our outreach programs and awareness campaigns',
      },
      {
        value: 50,
        description: 'Enable us to expand our search capabilities and reach',
      },
    ]
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e

    const proceedToCheckout = () => {
      router.push({
        name: 'Checkout',
        query: {
          amount: selectedAmount.value,
<<<<<<< HEAD
          type: 'donation'
        }
      });
    };
=======
          type: 'donation',
        },
      })
    }
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e

    return {
      selectedAmount,
      customAmount,
      frequency,
      donationAmounts,
<<<<<<< HEAD
      proceedToCheckout
    };
  }
};
=======
      proceedToCheckout,
    }
  },
}
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
</script>

<style scoped>
.donation-page {
  background-color: #f2f0e9;
  min-height: 100vh;
}

.donation-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 40px 20px;
}

.donation-form {
  max-width: 800px;
  margin: 60px auto;
  padding: 40px;
  background: white;
  border-radius: 20px;
<<<<<<< HEAD
  box-shadow: 0 4px 20px rgba(0,0,0,0.08);
=======
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
}

.section-title {
  font-size: 1.8rem;
  font-weight: 700;
<<<<<<< HEAD
  color: #2C3539;
=======
  color: #2c3539;
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
  margin-bottom: 30px;
  text-align: center;
}

.amount-options {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin-bottom: 30px;
}

.amount-option {
  padding: 20px;
  border: 2px solid #e0e0e0;
  border-radius: 12px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.amount-option:hover {
  border-color: #00bfff;
  transform: translateY(-2px);
}

.amount-option.selected {
  border-color: #00bfff;
<<<<<<< HEAD
  background: rgba(0,191,255,0.05);
=======
  background: rgba(0, 191, 255, 0.05);
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
}

.amount {
  font-size: 1.8em;
  font-weight: 700;
  color: #2c3e50;
  margin-bottom: 10px;
}

.description {
  font-size: 0.9em;
  color: #666;
  line-height: 1.4;
}

.custom-amount {
  padding: 20px;
  border: 2px solid #e0e0e0;
  border-radius: 12px;
}

.frequency-options {
  display: flex;
  justify-content: center;
  margin-bottom: 30px;
}

.donation-summary {
  text-align: center;
  padding: 20px;
  background: #f8f9fa;
  border-radius: 12px;
  margin-bottom: 30px;
}

.action-buttons {
  display: flex;
  justify-content: center;
  gap: 20px;
}

@media (max-width: 600px) {
  .donation-form {
    padding: 20px;
  }

  .amount-options {
    grid-template-columns: 1fr;
  }

  .section-title {
    font-size: 1.5rem;
  }

  .action-buttons {
    flex-direction: column;
  }

  .action-buttons .q-btn {
    width: 100%;
  }
}
<<<<<<< HEAD
</style> 
=======
</style>
>>>>>>> 258747401fa8e456b1547191cdae29be9cf3587e
