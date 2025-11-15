<template>
    <div class="font-sans text-gray-800 overflow-x-hidden">
        <HeroSection />
        <CoupleSection />
        <EventSection />
        <GallerySection />
        <LoveStorySection />
        <MusicPlayer />
        
        <!-- Modals -->
        <MapModal v-if="showMap" @close="showMap = false" />
        <ImageModal v-if="showImage" :image="selectedImage" @close="showImage = false" />
        <SuccessModal v-if="showSuccess" @close="showSuccess = false" />
    </div>
</template>

<script>
import HeroSection from './components/HeroSection.vue';
import CoupleSection from './components/CoupleSection.vue';
import EventSection from './components/EventSection.vue';
import GallerySection from './components/GallerySection.vue';
import LoveStorySection from './components/LoveStorySection.vue';
import RsvpSection from './components/RsvpSection.vue';
import Footer from './components/Footer.vue';
import MusicPlayer from './components/MusicPlayer.vue';
import MapModal from './components/Modal.vue';
import ImageModal from './components/Modal.vue';
import SuccessModal from './components/Modal.vue';

export default {
    name: 'App',
    components: {
        HeroSection,
        CoupleSection,
        EventSection,
        GallerySection,
        LoveStorySection,
        RsvpSection,
        Footer,
        MusicPlayer,
        MapModal,
        ImageModal,
        SuccessModal
    },
    data() {
        return {
            showMap: false,
            showImage: false,
            showSuccess: false,
            selectedImage: ''
        }
    },
    mounted() {
        // Initialize ScrollReveal
        setTimeout(() => {
            const sr = ScrollReveal({
                origin: 'bottom',
                distance: '30px',
                duration: 1000,
                delay: 200,
                easing: 'cubic-bezier(0.6, 0.2, 0.1, 1)',
                reset: false
            });
            
            sr.reveal('.fade-in');
            sr.reveal('.slide-in-left', { origin: 'left' });
            sr.reveal('.slide-in-right', { origin: 'right' });
            sr.reveal('.scale-in', { scale: 0.8 });
            sr.reveal('.rotate-in', { rotate: { x: 10, y: 10, z: 0 } });
        }, 100);
    }
}
</script>