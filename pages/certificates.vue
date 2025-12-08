<template>
  <main v-if="!loading" id="_certificates" class="page">

    <div id="mobile-page-title">
      <h2>_certificates</h2>
    </div>

    <div class="certificates-wrap">
      <div class="certificates-wrap">
        <div v-for="certificate in certificates" :key="certificate.id" class="certificate-container">
          <div class="certificate-img-container">
  <SkeletonImage
    :src="certificate.image"
    :alt="'Certificate ' + certificate.id"
    aspect="600/424"
  />
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
      certificates: [
        {
          id: 0,
          title: "Frontend Development with AI tools",
          date: "18.07.2025",
          image: "/images/certificates/epam-frontend.png",
          link: "#",
        },
        {
          id: 1,
          title: "Generative AI Development",
          date: "16.08.2024",
          image: "/images/certificates/gen-ai.png",
          link: "https://verified.sertifier.com/en/verify/25052450820962/",
        },
        {
          id: 2,
          title: "Google Cloud / ML learning",
          date: "24.02.2024",
          image: "/images/certificates/gc-ml.png",
          link: "https://verified.sertifier.com/en/verify/28260629628891/",
        },
        {
          id: 3,
          title: "Python Essentials 1",
          date: "12.12.2024",
          image: "/images/certificates/python-essentials-1.png",
          link: "https://www.credly.com/badges/920c19c0-290c-4773-be23-8e03f020d609/public_url",
        },
        {
          id: 4,
          title: "Interactive SQL Simulator",
          date: "02.04.2024",
          image: "/images/certificates/sql_stepik.png",
          link: "https://stepik.org/cert/2407297?lang=en",
        },
        {
          id: 5,
          title: "Managing Emotions in Times of Uncertainty & Stress",
          date: "02.04.2024",
          image: "/images/certificates/managing-emotions.jpeg",
          link: "https://coursera.org/share/3dc61461d81d4caebd9d041c5ad8f3e6",
        },
        {
          id: 6,
          title: "The Science of Well-Being",
          date: "14.04.2024",
          image: "/images/certificates/well-being.jpeg",
          link: "https://coursera.org/share/f63b9efa1aec7c300896870df60d8731",
        }
      ]
    };
  }
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
  width: 100%;
  user-select: none;
}

.certificate-img {
  width: 100%;
  height: auto;
  aspect-ratio: 600/424;
  transition: transform 0.5s ease;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.7);
}

</style>