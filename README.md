import { useEffect, useState } from 'react';
import Sidebar from '@/components/Sidebar';
import {
  Slide1,
  Slide2,
  Slide3,
  Slide4,
  Slide5,
  Slide6,
  Slide7,
  Slide8,
  Slide9,
  Slide10,
  RecommendedVideos,
  PPTPresentation,
} from '@/components/Slides';

export default function Home() {
  const [activeSection, setActiveSection] = useState('slide1');

  useEffect(() => {
    const handleScroll = () => {
      const sections = document.querySelectorAll('[id^="slide"]');
      let current = 'slide1';

      sections.forEach((section) => {
        const sectionTop = section.getBoundingClientRect().top;
        if (sectionTop <= window.innerHeight / 2) {
          current = section.getAttribute('id') || 'slide1';
        }
      });

      setActiveSection(current);
    };

    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  const handleNavigate = (sectionId: string) => {
    setActiveSection(sectionId);
  };

  return (
    <div className="flex min-h-screen bg-bg-dark">
      {/* Left Sidebar Navigation */}
      <Sidebar activeSection={activeSection} onNavigate={handleNavigate} />

      {/* Main Content */}
      <main className="ml-80 flex-1 flex flex-col">
        <Slide1 />
        <Slide2 />
        <Slide3 />
        <Slide4 />
        <Slide5 />
        <Slide6 />
        <Slide7 />
        <Slide8 />
        <Slide9 />
        <Slide10 />
        <RecommendedVideos />
        <PPTPresentation />
      </main>


    </div>
  );
}
