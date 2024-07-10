<template>
  <main v-if="!loading" id="_certificates" class="page">

    <div id="mobile-page-title">
      <h2>_certificates</h2>
    </div>

    <div class="certificates-wrap">
      <div class="certificate-container">
        <div class="certificate-img-container"
             ref="certificateImgContainer">
          <img src="/images/certificates/gc-ml.png" alt="Certificate1-google" class="certificate-img">
        </div>
        <div class="recipient-info">
          <a :href="certificateData.image">Google Cloud / ML learning</a>
          <p>{{ formattedDate }}</p>
        </div>
      </div>

      <div class="certificate-container">
        <div class="certificate-img-container"
             ref="certificateImgContainer">
          <img src="/images/certificates/sql_stepik.png" alt="Certificate2-stepik" class="certificate-img">
        </div>
        <div class="recipient-info">
          <a href="https://stepik.org/cert/2407297?lang=en">Interactive SQL Simulator</a>
          <p>02.04.2024</p>
        </div>
      </div>

      <div class="certificate-container">
        <div class="certificate-img-container"
             ref="certificateImgContainer">
          <img src="/images/certificates/managing-emotions.jpeg" alt="Certificate3-yale" class="certificate-img">
        </div>
        <div class="recipient-info">
          <a href="https://coursera.org/share/d4337e87f459ab1657f7da8c75ad3011">Managing Emotions in Times of Uncertainty & Stress</a>
          <p>02.04.2024</p>
        </div>
      </div>

      <div class="certificate-container">
        <div class="certificate-img-container"
             ref="certificateImgContainer">
          <img src="/images/certificates/well-being.jpeg" alt="Certificate4-yale" class="certificate-img">
        </div>
        <div class="recipient-info">
          <a href="https://coursera.org/share/f63b9efa1aec7c300896870df60d8731">The Science of Well-Being</a>
          <p>14.04.2024</p>
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
      certificateData: {
        "@context": "https://w3id.org/openbadges/v2",
        "type":"Assertion",
        "id":"https://api-lb.appfurther.io/v2/ims/28260629628891",
        "badge":"https://api-lb.appfurther.io/v2/ims/badgeClass/28260629628891",
        "image":"https://api-lb.appfurther.io/v2/ims/image/28260629628891",
        "verification":{"type":"HostedBadge"},
        "issuedOn":"2024-02-24T08:00:07.276Z",
        "recipient": {
          "type":"email",
          "hashed":false,
          "identity":"vladikobdk@gmail.com"
        },
        "evidence":[]
      }
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

