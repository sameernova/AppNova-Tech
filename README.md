import { useState } from "react";
import { motion } from "framer-motion";
import { Button } from "@/components/ui/button";
import { Sun, Moon } from "lucide-react";

export default function Home() {
  const [darkMode, setDarkMode] = useState(false);

  return (
    <div className={darkMode ? "bg-gray-900 text-white" : "bg-white text-gray-900"}>
      {/* Navbar */}
      <nav className="flex justify-between items-center p-6 shadow-md">
        <h1 className="text-3xl font-bold text-gradient">AppNova Tech</h1>
        <Button onClick={() => setDarkMode(!darkMode)}>
          {darkMode ? <Sun size={20} /> : <Moon size={20} />}
        </Button>
      </nav>

      {/* Hero Section */}
      <section className="h-screen flex flex-col items-center justify-center text-center p-10">
        <motion.h1
          className="text-6xl font-extrabold"
          initial={{ opacity: 0, y: -20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 1 }}
        >
          Welcome to <span className="text-gradient">AppNova Tech</span>
        </motion.h1>
        <p className="text-xl mt-4 max-w-2xl">
          We build cutting-edge mobile and web applications with futuristic technology and seamless user experience.
        </p>
        <Button className="mt-6 px-6 py-3 text-lg bg-blue-500 hover:bg-blue-600 rounded-xl shadow-lg">
          Get Started
        </Button>
      </section>

      {/* Services Section */}
      <section className="py-20 px-10 text-center">
        <h2 className="text-4xl font-bold mb-10">Our Services</h2>
        <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          {[
            { title: "Mobile App Development", description: "Innovative and scalable mobile applications for iOS & Android." },
            { title: "Web Development", description: "Modern, responsive, and high-performance web applications." },
            { title: "UI/UX Design", description: "Beautiful, user-friendly designs for an exceptional experience." },
            { title: "AI & Automation", description: "Integrating AI to enhance your applications and workflows." },
            { title: "Cloud Solutions", description: "Scalable and secure cloud-based infrastructures." },
            { title: "E-commerce Solutions", description: "Robust e-commerce platforms to drive online business growth." },
          ].map((service, index) => (
            <motion.div
              key={index}
              className="p-6 bg-gray-800 text-white rounded-xl shadow-lg hover:scale-105 transition-transform"
              initial={{ opacity: 0, y: 20 }}
              whileInView={{ opacity: 1, y: 0 }}
              transition={{ duration: 0.5, delay: index * 0.1 }}
            >
              <h3 className="text-2xl font-semibold mb-2">{service.title}</h3>
              <p>{service.description}</p>
            </motion.div>
          ))}
        </div>
      </section>

      {/* Portfolio Section */}
      <section className="py-20 px-10 text-center">
        <h2 className="text-4xl font-bold mb-10">Our Portfolio</h2>
        <p className="text-lg mb-6">Take a look at some of our latest projects.</p>
        <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          {Array(6).fill(0).map((_, index) => (
            <motion.div
              key={index}
              className="p-6 bg-gray-800 text-white rounded-xl shadow-lg hover:scale-105 transition-transform"
              initial={{ opacity: 0, y: 20 }}
              whileInView={{ opacity: 1, y: 0 }}
              transition={{ duration: 0.5, delay: index * 0.1 }}
            >
              <h3 className="text-2xl font-semibold mb-2">Project {index + 1}</h3>
              <p>A cutting-edge solution for our clients.</p>
            </motion.div>
          ))}
        </div>
      </section>

      {/* Footer */}
      <footer className="text-center py-10 bg-gray-800 text-white">
        <p>&copy; 2025 AppNova Tech. All Rights Reserved.</p>
      </footer>
    </div>
  );
}
