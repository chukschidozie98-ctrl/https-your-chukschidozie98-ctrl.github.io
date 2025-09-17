# https-your-chukschidozie98-ctrl.github.io
// Single-file React + Tailwind personal website
// Filename suggestion: PersonalPortfolio.jsx
// How to use:
// - This component is a single-file React page using Tailwind classes.
// - It uses framer-motion for simple animations. Ensure you have 'framer-motion' in your project.
// - Tailwind must be configured in your project. This component assumes Tailwind is available.
// - Replace placeholder text, images, and links with your real content.

import React from "react";
import { motion } from "framer-motion";

export default function PersonalPortfolio({
  siteTitle = "Lighta App",
  tagline = "Lighta",
  heroImage = null,
  primaryColor = "indigo-600",
}) {
  return (
    <div className="min-h-screen bg-white text-slate-800 antialiased">
      <header className="max-w-6xl mx-auto px-6 py-6 flex items-center justify-between">
        <div className="flex items-center gap-3">
          <div className={`w-10 h-10 rounded-lg bg-${primaryColor} flex items-center justify-center text-white font-bold`}>Y</div>
          <div>
            <h1 className="text-lg font-semibold">{siteTitle}</h1>
            <p className="text-sm text-slate-500">{tagline}</p>
          </div>
        </div>
        <nav className="hidden md:flex gap-6 items-center text-sm text-slate-700">
          <a href="#about">About</a>
          <a href="#work">Work</a>
          <a href="#services">Services</a>
          <a href="#contact" className={`px-3 py-2 rounded-md bg-${primaryColor} text-white`}>Contact</a>
        </nav>
        <button className="md:hidden p-2 rounded-md bg-slate-100">Menu</button>
      </header>

      <main className="max-w-6xl mx-auto px-6">
        <section className="grid grid-cols-1 md:grid-cols-2 gap-8 items-center py-12">
          <motion.div initial={{ x: -40, opacity: 0 }} animate={{ x: 0, opacity: 1 }} transition={{ duration: 0.6 }}>
            <h2 className="text-4xl font-extrabold leading-tight">Hi — I’m {siteTitle}.</h2>
            <p className="mt-4 text-lg text-slate-600">I build clean, modern websites and digital experiences. I care about design, performance and accessibility.</p>

            <div className="mt-6 flex gap-3">
              <a href="#work" className={`inline-block px-5 py-3 rounded-lg bg-${primaryColor} text-white shadow`}>View my work</a>
              <a href="#contact" className="inline-block px-5 py-3 rounded-lg border border-slate-200">Get in touch</a>
            </div>

            <div className="mt-8 grid grid-cols-2 gap-3 text-sm text-slate-600">
              <div>
                <strong className="block text-slate-900">Location</strong>
                Lagos, Nigeria
              </div>
              <div>
                <strong className="block text-slate-900">Availability</strong>
                Open to work
              </div>
            </div>
          </motion.div>

          <motion.div initial={{ scale: 0.95, opacity: 0 }} animate={{ scale: 1, opacity: 1 }} transition={{ duration: 0.6 }} className="flex justify-center">
            <div className="w-full max-w-sm rounded-2xl overflow-hidden shadow-lg bg-slate-50 flex items-center justify-center" style={{ height: 300 }}>
              {heroImage ? (
                <img src={heroImage} alt="Hero" className="object-cover w-full h-full" />
              ) : (
                <div className="text-center p-6">
                  <div className="text-6xl font-black text-slate-300">🙂</div>
                  <p className="mt-3 text-slate-500">Your hero image or product screenshot</p>
                </div>
              )}
            </div>
          </motion.div>
        </section>

        <section id="about" className="py-12 border-t border-slate-100">
          <h3 className="text-2xl font-bold">About me</h3>
          <p className="mt-4 text-slate-600">I’m a full‑stack developer and designer focused on usable interfaces and fast front-ends. I enjoy working with small teams and startups to ship products that delight users.</p>

          <div className="mt-6 grid grid-cols-1 md:grid-cols-3 gap-4">
            <div className="p-4 rounded-lg bg-slate-50 shadow-sm">
              <h4 className="font-semibold">Skills</h4>
              <ul className="mt-2 text-sm text-slate-600">
                <li>React • Next.js</li>
                <li>TypeScript • Node.js</li>
                <li>Design systems • Figma</li>
              </ul>
            </div>

            <div className="p-4 rounded-lg bg-slate-50 shadow-sm">
              <h4 className="font-semibold">Experience</h4>
              <p className="mt-2 text-sm text-slate-600">3+ years building web products with a focus on performance and UX.</p>
            </div>

            <div className="p-4 rounded-lg bg-slate-50 shadow-sm">
              <h4 className="font-semibold">Education</h4>
              <p className="mt-2 text-sm text-slate-600">Computer Science / Self-taught designer</p>
            </div>
          </div>
        </section>

        <section id="work" className="py-12 border-t border-slate-100">
          <h3 className="text-2xl font-bold">Selected work</h3>
          <p className="mt-2 text-slate-600">A few projects I’m proud of.</p>

          <div className="mt-6 grid grid-cols-1 md:grid-cols-3 gap-6">
            {Array.from({ length: 3 }).map((_, i) => (
              <article key={i} className="rounded-lg overflow-hidden shadow hover:shadow-md transition">
                <div className="h-40 bg-slate-100 flex items-center justify-center">Project {i + 1} image</div>
                <div className="p-4">
                  <h4 className="font-semibold">Project Title {i + 1}</h4>
                  <p className="mt-2 text-sm text-slate-600">One-line project description that highlights the impact.</p>
                  <div className="mt-3 flex gap-2 text-xs">
                    <span className="px-2 py-1 rounded bg-slate-100">React</span>
                    <span className="px-2 py-1 rounded bg-slate-100">API</span>
                  </div>
                </div>
              </article>
            ))}
          </div>
        </section>

        <section id="services" className="py-12 border-t border-slate-100">
          <h3 className="text-2xl font-bold">Services</h3>
          <div className="mt-6 grid grid-cols-1 md:grid-cols-3 gap-6">
            <div className="p-6 rounded-lg border">
              <h4 className="font-semibold">Web Development</h4>
              <p className="mt-2 text-sm text-slate-600">Modern, responsive websites and web apps.</p>
            </div>
            <div className="p-6 rounded-lg border">
              <h4 className="font-semibold">Design Systems</h4>
              <p className="mt-2 text-sm text-slate-600">Reusable UI and strong visual language.</p>
            </div>
            <div className="p-6 rounded-lg border">
              <h4 className="font-semibold">Consulting</h4>
              <p className="mt-2 text-sm text-slate-600">Product and UX advice for early-stage teams.</p>
            </div>
          </div>
        </section>

        <section id="contact" className="py-12 border-t border-slate-100">
          <h3 className="text-2xl font-bold">Get in touch</h3>
          <p className="mt-2 text-slate-600">Want to work together? Drop me a message.</p>

          <form className="mt-6 max-w-xl">
            <div className="grid grid-cols-1 md:grid-cols-2 gap-3">
              <input className="p-3 rounded border border-slate-200" placeholder="Your name" />
              <input className="p-3 rounded border border-slate-200" placeholder="Email" />
            </div>
            <textarea className="mt-3 w-full p-3 rounded border border-slate-200" rows={5} placeholder="Tell me about your project"></textarea>
            <div className="mt-3 flex items-center gap-3">
              <button type="button" className={`px-4 py-2 rounded bg-${primaryColor} text-white`}>Send message</button>
              <span className="text-sm text-slate-500">Or email me at <a href="mailto:you@example.com" className="underline">you@example.com</a></span>
            </div>
          </form>
        </section>

        <footer className="mt-12 py-8 border-t border-slate-100 text-sm text-slate-500">
          <div className="max-w-6xl mx-auto px-6 flex flex-col md:flex-row justify-between items-center">
            <div>© {new Date().getFullYear()} {siteTitle}. All rights reserved.</div>
            <div className="mt-3 md:mt-0">Built with React + Tailwind</div>
          </div>
        </footer>
      </main>
    </div>
  );
}


