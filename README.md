# G-silicon-oo
git init
git add .
git commit -m "Initial commit"
import React, { useState, useEffect } from "react";
import { Lightbulb, Users, Briefcase, Mail } from "lucide-react";

export default function GSiliconWebsite() {
  const [menuOpen, setMenuOpen] = useState(false);
  const [showScrollTop, setShowScrollTop] = useState(false);
  const [scrollClass, setScrollClass] = useState("");

  useEffect(() => {
    const handleScroll = () => {
      setShowScrollTop(window.scrollY > 300);
      setScrollClass("animate-fade-in-up");
    };
    window.addEventListener("scroll", handleScroll);
    return () => window.removeEventListener("scroll", handleScroll);
  }, []);

  const scrollToTop = () => {
    window.scrollTo({ top: 0, behavior: "smooth" });
  };

  return (
    <div className="bg-white text-gray-900 font-sans scroll-smooth relative">
      {/* Navigation Bar */}
      <header className="bg-white shadow sticky top-0 z-50 transition-all duration-300">
        <div className="max-w-7xl mx-auto px-4 py-4 flex justify-between items-center">
          <h1 className="text-xl font-bold text-blue-700">G-Silicon</h1>
          <nav className="hidden md:flex space-x-6 text-sm md:text-base">
            <a href="#about" className="text-gray-700 hover:text-blue-700">About</a>
            <a href="#services" className="text-gray-700 hover:text-blue-700">Services</a>
            <a href="#portfolio" className="text-gray-700 hover:text-blue-700">Portfolio</a>
            <a href="#careers" className="text-gray-700 hover:text-blue-700">Careers</a>
            <a href="#contact" className="text-gray-700 hover:text-blue-700">Contact</a>
          </nav>
          <button
            className="md:hidden text-blue-700 focus:outline-none"
            onClick={() => setMenuOpen(!menuOpen)}
          >
            ☰
          </button>
        </div>
        {menuOpen && (
          <div className="md:hidden bg-white shadow px-4 pb-4 space-y-2 animate-slide-down">
            <a href="#about" onClick={() => setMenuOpen(false)} className="block text-gray-700 hover:text-blue-700">About</a>
            <a href="#services" onClick={() => setMenuOpen(false)} className="block text-gray-700 hover:text-blue-700">Services</a>
            <a href="#portfolio" onClick={() => setMenuOpen(false)} className="block text-gray-700 hover:text-blue-700">Portfolio</a>
            <a href="#careers" onClick={() => setMenuOpen(false)} className="block text-gray-700 hover:text-blue-700">Careers</a>
            <a href="#contact" onClick={() => setMenuOpen(false)} className="block text-gray-700 hover:text-blue-700">Contact</a>
          </div>
        )}
      </header>

      {/* Hero Section */}
      <section className={`text-center py-20 px-4 bg-gradient-to-br from-blue-600 to-indigo-700 text-white ${scrollClass}`}>
        <h1 className="text-4xl md:text-5xl font-bold mb-4">Accelerating Silicon Success. One Design at a Time.</h1>
        <p className="text-lg md:text-xl mb-6">Your trusted partner in end-to-end ASIC design services — from RTL to GDSII.</p>
        <div className="space-x-4">
          <a href="#services" className="inline-block bg-white text-blue-700 font-semibold px-6 py-2 rounded-xl shadow">Explore Our Services</a>
          <a href="#careers" className="inline-block border border-white px-6 py-2 rounded-xl">Work With Us</a>
        </div>
      </section>

      {/* What We Are */}
      <section id="about" className={`max-w-5xl mx-auto py-16 px-6 opacity-0 animate-fade-in-up flex items-start space-x-6`}>
        <Users className="text-blue-700 w-10 h-10 shrink-0 mt-1" />
        <div>
          <h2 className="text-3xl font-bold mb-4">What We Are</h2>
          <p className="text-lg">We are a team of passionate semiconductor professionals driven by a shared vision to build the future of chip design. At G-Silicon, we combine technical rigor with design innovation to help clients transform ideas into market-ready silicon.</p>
        </div>
      </section>

      {/* What We Think */}
      <section className={`max-w-5xl mx-auto py-16 px-6 opacity-0 animate-fade-in-up flex items-start space-x-6`}>
        <Lightbulb className="text-yellow-500 w-10 h-10 shrink-0 mt-1" />
        <div>
          <h2 className="text-3xl font-bold mb-4">What We Think</h2>
          <p className="text-lg">We believe the next wave of semiconductor breakthroughs will be built on collaboration, speed, and scalable talent. Our approach is people-first, quality-obsessed, and execution-focused — because in silicon, precision is everything.</p>
        </div>
      </section>

      {/* Portfolio */}
      <section id="portfolio" className={`bg-white py-16 px-6 ${scrollClass}`}>
        <div className="max-w-5xl mx-auto text-center">
          <Briefcase className="w-10 h-10 text-blue-700 mx-auto mb-4" />
          <h2 className="text-3xl font-bold mb-6">Our Portfolio</h2>
          <p className="text-lg mb-6">Explore our latest projects across ASIC design, verification, and digital transformation initiatives.</p>
          <div className="grid md:grid-cols-3 gap-6 text-left">
            <div className="bg-gray-100 p-4 rounded-xl shadow">High-performance CPU SoC – RTL to GDSII in 7nm</div>
            <div className="bg-gray-100 p-4 rounded-xl shadow">Automotive ASIC Design Verification with UVM</div>
            <div className="bg-gray-100 p-4 rounded-xl shadow">Mobile App UI/UX for Fintech Startup</div>
          </div>
        </div>
      </section>

      {/* Careers */}
      <section id="careers" className={`max-w-5xl mx-auto py-16 px-6 ${scrollClass}`}>
        <h2 className="text-3xl font-bold mb-4">Careers</h2>
        <p className="text-lg mb-6">Join G-Silicon and work on high-impact, real-world projects in cutting-edge semiconductor technology. Whether you’re a seasoned engineer or a fresher, we offer a supportive environment and excellent growth opportunities.</p>
        <ul className="list-disc pl-6 space-y-2">
          <li>Hands-on ASIC design experience</li>
          <li>Mentorship & career growth</li>
          <li>Engineering-led culture</li>
          <li>Competitive compensation</li>
        </ul>
        <form className="mt-8 bg-gray-100 p-6 rounded-xl shadow space-y-4">
          <h3 className="text-xl font-semibold">Job Application Form</h3>
          <input type="text" placeholder="Full Name" className="w-full border p-2 rounded" />
          <input type="email" placeholder="Email" className="w-full border p-2 rounded" />
          <input type="file" className="w-full" />
          <textarea placeholder="Why do you want to join us?" className="w-full border p-2 rounded" rows="4"></textarea>
          <button className="bg-blue-700 text-white px-4 py-2 rounded-xl">Submit Application</button>
        </form>
      </section>

      {/* Contact */}
      <section id="contact" className={`bg-gray-100 py-16 px-6 text-center ${scrollClass}`}>
        <h2 className="text-3xl font-bold mb-4">Contact Us</h2>
        <p className="mb-2">📍 3rd Floor, Cyber Tower, Software Layout, HSR Layout, Bangalore - 560102</p>
        <p className="mb-2">📧 contact@gsilicon.com</p>
        <p className="mb-6">📞 +91-6366 245 874</p>
        <form className="max-w-xl mx-auto bg-white p-6 rounded-xl shadow space-y-4">
          <h3 className="text-xl font-semibold text-left">Service Inquiry Form</h3>
          <input type="text" placeholder="Name" className="w-full border p-2 rounded" />
          <input type="email" placeholder="Email" className="w-full border p-2 rounded" />
          <textarea placeholder="Tell us about your project..." className="w-full border p-2 rounded" rows="4"></textarea>
          <button className="bg-indigo-700 text-white px-4 py-2 rounded-xl">Send Inquiry</button>
        </form>
      </section>

      {/* Scroll to Top Button */}
      {showScrollTop && (
        <button
          onClick={scrollToTop}
          className="fixed bottom-6 right-6 bg-blue-700 text-white px-4 py-2 rounded-full shadow-lg hover:bg-blue-800 transition"
        >
          ↑ Top
        </button>
      )}
    </div>
  );
}
