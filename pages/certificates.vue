<template>
  <main v-if="!loading" id="_certificates" class="page">

    <div id="mobile-page-title">
      <h2>_certificates</h2>
    </div>

    <div class="certificates-wrap">
      <div class="certificates-wrap">
        <div v-for="certificate in certificates" :key="certificate.id" class="certificate-container">
          <div class="certificate-img-container" ref="certificateImgContainer">
            <img :src="certificate.image" :alt="'Certificate' + certificate.id" class="certificate-img">
          </div>
          <div class="recipient-info">
            <a :href="certificate.link" target="_blank">{{ certificate.title }}</a>
            <p>{{ certificate.date }}</p>
          </div>
        </div>
      </div>
    </div>

  </main>
</template>

<script>
export default {
  data() {
    return {
      loading: false,
      stopRotationBound: null,
      // certificateData: {
      //   "@context": "https://w3id.org/openbadges/v2",
      //   "type":"Assertison",
      //   "id":"https://api-lb.appfurther.io/v2/ims/28260629628891",
      //   "badge":"https://api-lb.appfurther.io/v2/ims/badgeClass/28260629628891",
      //   "image":"https://api-lb.appfurther.io/v2/ims/image/28260629628891",
      //   "verification":{"type":"HostedBadge"},
      //   "issuedOn":"2024-02-24T08:00:07.276Z",
      //   "recipient": {
      //     "type":"email",
      //     "hashed":false,
      //     "identity":"vladikobdk@gmail.com"
      //   },
      //   "evidence":[]
      // },
      certificates: [
        {
          id: 1,
          title: "Google Cloud / ML learning",
          date: "24.02.2024",
          image: "/images/certificates/gc-ml.png",
          link: "https://verified.sertifier.com/en/verify/28260629628891/?ref=email"
        },
        {
          id: 2,
          title: "Interactive SQL Simulator",
          date: "02.04.2024",
          image: "/images/certificates/sql_stepik.png",
          link: "https://stepik.org/cert/2407297?lang=en"
        },
        {
          id: 3,
          title: "Managing Emotions in Times of Uncertainty & Stress",
          date: "02.04.2024",
          image: "/images/certificates/managing-emotions.jpeg",
          link: "https://coursera.org/share/3dc61461d81d4caebd9d041c5ad8f3e6"
        },
        {
          id: 4,
          title: "The Science of Well-Being",
          date: "14.04.2024",
          image: "/images/certificates/well-being.jpeg",
          link: "https://coursera.org/share/f63b9efa1aec7c300896870df60d8731"
        }
      ]
    };
  },
  computed: {
    formattedDate() {
      const date = new Date(this.certificateData.issuedOn);
      return date.toLocaleDateString();
    }
  },
};
</script>

<style scoped>
.page {
  overflow: auto;
}

.certificates-wrap {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.certificate-container {
  margin: 20px auto;
}

.recipient-info {
  margin-top: 20px;
}

.recipient-info a,
.recipient-info p {
  margin: 5px 0;
  text-align: center;
  color: white;
}

.recipient-info a {
  display: block;
  text-decoration: underline;
}

.certificate-img-container {
  max-width: 600px;
  user-select: none;
}

.certificate-img {
  width: 100%;
  height: auto;
  transition: transform 0.5s ease;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.7);
}



</style>

