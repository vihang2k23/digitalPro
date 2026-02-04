<template>
  <div class="min-h-screen bg-gray-50">
    <!-- Hero Section -->
    <section class="py-20 bg-gradient-to-br from-primary-50 via-white to-secondary-50">
      <div class="container mx-auto px-4">
        <div class="text-center max-w-4xl mx-auto">
          <h1 class="text-4xl md:text-6xl font-bold mb-6">
            <span class="gradient-text">Privacy Policy</span>
          </h1>
          <p class="text-xl text-gray-600">
            Your privacy is important to us. This policy explains how we collect, use, and protect your information.
          </p>
        </div>
      </div>
    </section>

    <!-- Privacy Content -->
    <section class="py-20">
      <div class="container mx-auto px-4 max-w-4xl">
        <div class="bg-white rounded-xl shadow-lg p-8 md:p-12">
          <div class="prose prose-lg max-w-none">
            <!-- Last Updated -->
            <div class="bg-gray-100 rounded-lg p-4 mb-8">
              <p class="text-sm text-gray-600">
                <strong>Last Updated:</strong> {{ lastUpdated }}
              </p>
            </div>

            <!-- Introduction -->
            <div class="mb-8">
              <h2 class="text-2xl font-bold mb-4 text-gray-900">1. Introduction</h2>
              <p class="text-gray-700 leading-relaxed mb-4">
                Welcome to DigitalPro. We respect your privacy and are committed to protecting your personal data. This privacy policy will inform you about how we look after your personal data when you visit our website and tell you about your privacy rights and how the law protects you.
              </p>
            </div>

            <!-- Information We Collect -->
            <div class="mb-8">
              <h2 class="text-2xl font-bold mb-4 text-gray-900">2. Information We Collect</h2>
              
              <h3 class="text-xl font-semibold mb-3 text-gray-800">2.1 Personal Information</h3>
              <ul class="list-disc pl-6 mb-4 space-y-2 text-gray-700">
                <li>Name and contact information (email, phone number, address)</li>
                <li>Company information and job title</li>
                <li>Communication preferences</li>
                <li>Account credentials (if applicable)</li>
              </ul>

              <h3 class="text-xl font-semibold mb-3 text-gray-800">2.2 Technical Information</h3>
              <ul class="list-disc pl-6 mb-4 space-y-2 text-gray-700">
                <li>IP address and device information</li>
                <li>Browser type and version</li>
                <li>Operating system</li>
                <li>Cookies and similar tracking technologies</li>
                <li>Pages visited and time spent on our website</li>
              </ul>

              <h3 class="text-xl font-semibold mb-3 text-gray-800">2.3 Business Information</h3>
              <ul class="list-disc pl-6 space-y-2 text-gray-700">
                <li>Company size and industry</li>
                <li>Marketing budget and requirements</li>
                <li>Project details and specifications</li>
                <li>Business goals and objectives</li>
              </ul>
            </div>

            <!-- How We Use Your Information -->
            <div class="mb-8">
              <h2 class="text-2xl font-bold mb-4 text-gray-900">3. How We Use Your Information</h2>
              <p class="text-gray-700 leading-relaxed mb-4">
                We use your personal information for various purposes, including:
              </p>
              <ul class="list-disc pl-6 space-y-2 text-gray-700">
                <li><strong>Service Provision:</strong> To provide and manage our digital marketing services</li>
                <li><strong>Communication:</strong> To respond to your inquiries and send relevant updates</li>
                <li><strong>Marketing:</strong> To send you information about our services and promotional offers</li>
                <li><strong>Improvement:</strong> To analyze and improve our website and services</li>
                <li><strong>Legal Compliance:</strong> To comply with legal obligations and protect our rights</li>
                <li><strong>Analytics:</strong> To understand user behavior and preferences</li>
              </ul>
            </div>

            <!-- Data Sharing -->
            <div class="mb-8">
              <h2 class="text-2xl font-bold mb-4 text-gray-900">4. Data Sharing and Disclosure</h2>
              <p class="text-gray-700 leading-relaxed mb-4">
                We may share your personal information with:
              </p>
              <ul class="list-disc pl-6 space-y-2 text-gray-700">
                <li><strong>Service Providers:</strong> Third-party companies that help us operate our business</li>
                <li><strong>Business Partners:</strong> Trusted partners with whom we jointly offer services</li>
                <li><strong>Legal Authorities:</strong> When required by law or to protect our rights</li>
                <li><strong>Business Transfers:</strong> In case of merger, acquisition, or sale of assets</li>
              </ul>
              <p class="text-gray-700 leading-relaxed mt-4">
                We never sell your personal information to third parties for marketing purposes.
              </p>
            </div>

            <!-- Data Security -->
            <div class="mb-8">
              <h2 class="text-2xl font-bold mb-4 text-gray-900">5. Data Security</h2>
              <p class="text-gray-700 leading-relaxed mb-4">
                We implement appropriate technical and organizational measures to protect your personal data against unauthorized access, alteration, disclosure, or destruction. These include:
              </p>
              <ul class="list-disc pl-6 space-y-2 text-gray-700">
                <li>SSL encryption for data transmission</li>
                <li>Secure servers and databases</li>
                <li>Regular security audits and updates</li>
                <li>Employee training on data protection</li>
                <li>Access controls and authentication systems</li>
              </ul>
            </div>

            <!-- Your Rights -->
            <div class="mb-8">
              <h2 class="text-2xl font-bold mb-4 text-gray-900">6. Your Rights</h2>
              <p class="text-gray-700 leading-relaxed mb-4">
                You have the following rights regarding your personal data:
              </p>
              <ul class="list-disc pl-6 space-y-2 text-gray-700">
                <li><strong>Access:</strong> Request access to your personal data</li>
                <li><strong>Correction:</strong> Request correction of inaccurate data</li>
                <li><strong>Deletion:</strong> Request deletion of your personal data</li>
                <li><strong>Portability:</strong> Request transfer of your data to another service</li>
                <li><strong>Objection:</strong> Object to processing of your data</li>
                <li><strong>Restriction:</strong> Request restriction of processing</li>
              </ul>
            </div>

            <!-- Cookies -->
            <div class="mb-8">
              <h2 class="text-2xl font-bold mb-4 text-gray-900">7. Cookies and Tracking</h2>
              <p class="text-gray-700 leading-relaxed mb-4">
                We use cookies and similar tracking technologies to enhance your experience on our website. Cookies are small files stored on your device that help us:
              </p>
              <ul class="list-disc pl-6 space-y-2 text-gray-700">
                <li>Remember your preferences</li>
                <li>Analyze website traffic and usage</li>
                <li>Personalize content and advertisements</li>
                <li>Improve website functionality</li>
              </ul>
              <p class="text-gray-700 leading-relaxed mt-4">
                You can control cookies through your browser settings, but disabling cookies may affect website functionality.
              </p>
            </div>

            <!-- Third-Party Links -->
            <div class="mb-8">
              <h2 class="text-2xl font-bold mb-4 text-gray-900">8. Third-Party Websites</h2>
              <p class="text-gray-700 leading-relaxed">
                Our website may contain links to third-party websites. We are not responsible for the privacy practices of these websites. We encourage you to review their privacy policies before providing any personal information.
              </p>
            </div>

            <!-- Children's Privacy -->
            <div class="mb-8">
              <h2 class="text-2xl font-bold mb-4 text-gray-900">9. Children's Privacy</h2>
              <p class="text-gray-700 leading-relaxed">
                Our services are not intended for children under 13 years of age. We do not knowingly collect personal information from children under 13. If we become aware that we have collected such information, we will take steps to delete it promptly.
              </p>
            </div>

            <!-- Changes to Policy -->
            <div class="mb-8">
              <h2 class="text-2xl font-bold mb-4 text-gray-900">10. Changes to This Policy</h2>
              <p class="text-gray-700 leading-relaxed">
                We may update this privacy policy from time to time. We will notify you of any changes by posting the new policy on this page and updating the "Last Updated" date. We encourage you to review this policy periodically.
              </p>
            </div>

            <!-- Contact Information -->
            <div class="mb-8">
              <h2 class="text-2xl font-bold mb-4 text-gray-900">11. Contact Us</h2>
              <p class="text-gray-700 leading-relaxed mb-4">
                If you have any questions about this privacy policy or how we handle your personal data, please contact us:
              </p>
              <div class="bg-gray-50 rounded-lg p-6">
                <ul class="space-y-2 text-gray-700">
                  <li><strong>Email:</strong> privacy@digitalpro.com</li>
                  <li><strong>Phone:</strong> +1 (555) 123-4567</li>
                  <li><strong>Address:</strong> 123 Business Ave, Suite 100, New York, NY 10001</li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'

const lastUpdated = ref(new Date().toLocaleDateString('en-US', { 
  year: 'numeric', 
  month: 'long', 
  day: 'numeric' 
}))

onMounted(() => {
  // Animate content sections
  gsap.utils.toArray('.prose > div').forEach((section: any, index: number) => {
    gsap.fromTo(section,
      { opacity: 0, y: 30 },
      {
        opacity: 1,
        y: 0,
        duration: 0.6,
        delay: index * 0.1,
        ease: "power2.out"
      }
    )
  })
})
</script>

<style scoped>
.prose h2 {
  @apply border-b border-gray-200 pb-2 mb-4;
}

.prose h3 {
  @apply text-lg font-semibold;
}

.prose ul {
  @apply space-y-1;
}

.prose li {
  @apply leading-relaxed;
}
</style>
