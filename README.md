# abdoportfolio.github.ioimport React from "react";
import { motion } from "framer-motion";
import { Camera, Cube, Mail, Download, Github, Linkedin, Images, Star, Hammer } from "lucide-react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";

// === HOW TO USE ===
// 1) Replace the placeholder image URLs below (imageJuice, imageChocolate) with your own.
//    If you have your renders hosted (Google Drive/Imgur/ArtStation), paste the direct image URLs.
// 2) Replace social links (GITHUB_URL, LINKEDIN_URL, EMAIL_ADDRESS) with your real links.
// 3) Press “Export” in ChatGPT (Download) to save this as an .html/.tsx page for deployment.

const GITHUB_URL = "https://github.com/"; // ← optional
const LINKEDIN_URL = "https://www.linkedin.com/"; // ← optional
const EMAIL_ADDRESS = "abdelhadi@example.com"; // ← replace with your email
const CV_URL = "#"; // ← link to your CV/Resume PDF if you have one

// Placeholder images — replace these with your 8K or portfolio links
const imageJuice =
  "https://images.unsplash.com/photo-1541976076758-347942db1970?q=80&w=1600&auto=format&fit=crop";
const imageChocolate =
  "https://images.unsplash.com/photo-1548907040-4baa42d1092a?q=80&w=1600&auto=format&fit=crop";

const Section = ({ id, title, children }) => (
  <section id={id} className="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
    <motion.h2
      initial={{ opacity: 0, y: 12 }}
      whileInView={{ opacity: 1, y: 0 }}
      viewport={{ once: true }}
      className="text-3xl sm:text-4xl font-bold tracking-tight mb-8"
    >
      {title}
    </motion.h2>
    {children}
  </section>
);

const SkillTag = ({ children }) => (
  <span className="inline-flex items-center gap-2 text-sm px-3 py-1.5 rounded-full bg-white/70 backdrop-blur shadow-sm border border-black/5">
    <Star className="w-4 h-4" /> {children}
  </span>
);

export default function Portfolio() {
  return (
    <div className="min-h-screen bg-gradient-to-b from-sky-50 via-white to-sky-50 text-gray-900">
      {/* Navbar */}
      <header className="sticky top-0 z-50 bg-white/80 backdrop-blur border-b border-black/5">
        <nav className="max-w-6xl mx-auto flex items-center justify-between px-4 sm:px-6 lg:px-8 h-16">
          <a href="#home" className="font-semibold tracking-tight">Abdelhadi Laouari</a>
          <div className="hidden sm:flex items-center gap-1">
            <a href="#work" className="px-3 py-2 rounded-xl hover:bg-sky-50">Work</a>
            <a href="#about" className="px-3 py-2 rounded-xl hover:bg-sky-50">About</a>
            <a href="#skills" className="px-3 py-2 rounded-xl hover:bg-sky-50">Skills</a>
            <a href="#contact" className="px-3 py-2 rounded-xl hover:bg-sky-50">Contact</a>
          </div>
          <div className="flex items-center gap-2">
            <a href={`mailto:${EMAIL_ADDRESS}`} className="px-3 py-2 rounded-xl bg-sky-600 text-white hover:bg-sky-700">Hire Me</a>
          </div>
        </nav>
      </header>

      {/* Hero */}
      <section id="home" className="relative overflow-hidden">
        <div className="absolute inset-0 -z-10">
          <div className="absolute -top-32 -right-24 w-[36rem] h-[36rem] rounded-full bg-sky-200 blur-3xl opacity-50" />
          <div className="absolute -bottom-24 -left-24 w-[30rem] h-[30rem] rounded-full bg-indigo-200 blur-3xl opacity-50" />
        </div>
        <div className="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 py-24">
          <motion.div initial={{ opacity: 0, y: 12 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.6 }} className="grid md:grid-cols-2 gap-10 items-center">
            <div>
              <h1 className="text-4xl sm:text-5xl font-black leading-tight">
                3D Artist & Product Visualization
              </h1>
              <p className="mt-5 text-lg text-gray-700 leading-relaxed">
                I create <strong>photorealistic</strong> product models and cinematic renders using Blender (Cycles). 
                I handle the full pipeline: <em>modeling, UVs, texturing, shading, lighting, animation, and 8K rendering</em>.
              </p>
              <div className="mt-6 flex flex-wrap gap-3">
                <Button asChild className="rounded-2xl shadow">
                  <a href="#work"><Images className="w-4 h-4 mr-2"/> View Work</a>
                </Button>
                <Button asChild variant="outline" className="rounded-2xl">
                  <a href={CV_URL}><Download className="w-4 h-4 mr-2"/> Download CV</a>
                </Button>
              </div>
              <div className="mt-6 flex items-center gap-3">
                <a href={GITHUB_URL} className="p-2 rounded-xl hover:bg-sky-50"><Github/></a>
                <a href={LINKEDIN_URL} className="p-2 rounded-xl hover:bg-sky-50"><Linkedin/></a>
                <a href={`mailto:${EMAIL_ADDRESS}`} className="p-2 rounded-xl hover:bg-sky-50"><Mail/></a>
              </div>
            </div>
            <motion.div initial={{ opacity: 0, scale: 0.98 }} animate={{ opacity: 1, scale: 1 }} transition={{ delay: 0.1 }} className="relative">
              <div className="aspect-[4/3] rounded-3xl overflow-hidden shadow-2xl ring-1 ring-black/5">
                <img src={imageJuice} alt="Hero render" className="w-full h-full object-cover"/>
              </div>
              <div className="absolute -bottom-4 -right-4 bg-white rounded-2xl shadow px-4 py-3 border border-black/5 flex items-center gap-2">
                <Camera className="w-4 h-4"/> 8K Cycles Render
              </div>
            </motion.div>
          </motion.div>
        </div>
      </section>

      {/* Work */}
      <Section id="work" title="Selected Work">
        <div className="grid md:grid-cols-2 gap-6">
          {/* Project 1: Juice Can */}
          <Card className="rounded-3xl shadow-sm border-black/5">
            <CardContent className="p-0">
              <div className="aspect-[4/3] overflow-hidden rounded-t-3xl">
                <img src={imageJuice} alt="Photorealistic Juice Can by Abdelhadi" className="w-full h-full object-cover hover:scale-[1.02] transition"/>
              </div>
              <div className="p-6 space-y-3">
                <h3 className="text-xl font-semibold">Photorealistic Juice Can</h3>
                <p className="text-gray-700 leading-relaxed">
                  Modeled, UV unwrapped, textured, shaded, lit, and rendered entirely by me in Blender. Inspired by a real drink I had; recreated with custom materials and studio lighting for a commercial look. Rendered in <strong>8K Cycles</strong>.
                </p>
                <div className="flex flex-wrap gap-2 text-sm">
                  <SkillTag>Blender</SkillTag>
                  <SkillTag>Cycles</SkillTag>
                  <SkillTag>Product Viz</SkillTag>
                  <SkillTag>Materials</SkillTag>
                </div>
                <div className="pt-2 flex gap-3">
                  <Button asChild className="rounded-xl"><a href={imageJuice} target="_blank">Open Render</a></Button>
                  <Button asChild variant="outline" className="rounded-xl"><a href="#contact">Request Commission</a></Button>
                </div>
              </div>
            </CardContent>
          </Card>

          {/* Project 2: Chocolate */}
          <Card className="rounded-3xl shadow-sm border-black/5">
            <CardContent className="p-0">
              <div className="aspect-[4/3] overflow-hidden rounded-t-3xl">
                <img src={imageChocolate} alt="Photorealistic Chocolate by Abdelhadi" className="w-full h-full object-cover hover:scale-[1.02] transition"/>
              </div>
              <div className="p-6 space-y-3">
                <h3 className="text-xl font-semibold">Photorealistic Chocolate Bar</h3>
                <p className="text-gray-700 leading-relaxed">
                  Full scene built from scratch: chocolate model, wooden table, environment, custom shader with subtle SSS and roughness variation. Dramatic lighting for appetizing highlights. Rendered in <strong>8K Cycles</strong>.
                </p>
                <div className="flex flex-wrap gap-2 text-sm">
                  <SkillTag>Modeling</SkillTag>
                  <SkillTag>Shading</SkillTag>
                  <SkillTag>Lighting</SkillTag>
                  <SkillTag>Food Viz</SkillTag>
                </div>
                <div className="pt-2 flex gap-3">
                  <Button asChild className="rounded-xl"><a href={imageChocolate} target="_blank">Open Render</a></Button>
                  <Button asChild variant="outline" className="rounded-xl"><a href="#contact">Request Commission</a></Button>
                </div>
              </div>
            </CardContent>
          </Card>
        </div>
      </Section>

      {/* About */}
      <Section id="about" title="About Me">
        <div className="grid md:grid-cols-3 gap-8">
          <div className="md:col-span-2">
            <p className="text-lg leading-relaxed text-gray-700">
              I am Abdelhadi Laouari, a 3D artist from Algeria focused on <strong>photorealistic product visualization</strong> and 
              cinematic ads. I build everything myself — models, textures, materials, lighting setups, and final renders — 
              to deliver studio-quality results. My goal is to found <em>Abdelhadi Empire</em>, a creative studio, and to study and work internationally.
            </p>
            <ul className="mt-6 grid sm:grid-cols-2 gap-3 text-gray-800">
              <li className="flex items-center gap-3"><Cube className="w-5 h-5"/> Hard-surface & organic modeling</li>
              <li className="flex items-center gap-3"><Hammer className="w-5 h-5"/> Procedural + hand-painted texturing</li>
              <li className="flex items-center gap-3"><Camera className="w-5 h-5"/> Studio lighting & product staging</li>
              <li className="flex items-center gap-3"><Star className="w-5 h-5"/> 8K Cycles rendering & compositing</li>
            </ul>
          </div>
          <div>
            <div className="p-6 rounded-3xl bg-white shadow border border-black/5">
              <h4 className="font-semibold mb-3">Highlights</h4>
              <ul className="space-y-2 text-gray-700">
                <li>• All assets created from scratch</li>
                <li>• End‑to‑end workflow (model → render)</li>
                <li>• Optimized topology & UVs</li>
                <li>• Ready for animation/ads</li>
              </ul>
            </div>
          </div>
        </div>
      </Section>

      {/* Skills */}
      <Section id="skills" title="Tools & Skills">
        <div className="flex flex-wrap gap-3">
          <SkillTag>Blender</SkillTag>
          <SkillTag>Cycles</SkillTag>
          <SkillTag>UV Unwrapping</SkillTag>
          <SkillTag>Texturing</SkillTag>
          <SkillTag>Shading/Materials</SkillTag>
          <SkillTag>HDRI / Lighting</SkillTag>
          <SkillTag>Compositing</SkillTag>
          <SkillTag>8K Rendering</SkillTag>
          <SkillTag>After Effects</SkillTag>
          <SkillTag>Premiere Pro</SkillTag>
          <SkillTag>Photoshop</SkillTag>
        </div>
      </Section>

      {/* Contact */}
      <Section id="contact" title="Work with Me">
        <div className="grid md:grid-cols-2 gap-8 items-center">
          <div className="space-y-4">
            <p className="text-lg text-gray-700">
              I’m available for freelance product visualization, commercials, and high‑end 3D renders. 
              Send me your brief and I’ll reply with a proposal and timeline.
            </p>
            <div className="flex flex-wrap gap-3">
              <Button asChild className="rounded-2xl"><a href={`mailto:${EMAIL_ADDRESS}`}><Mail className="w-4 h-4 mr-2"/> Email Me</a></Button>
              <Button asChild variant="outline" className="rounded-2xl"><a href={LINKEDIN_URL}><Linkedin className="w-4 h-4 mr-2"/> LinkedIn</a></Button>
            </div>
          </div>
          <div className="p-6 rounded-3xl bg-white shadow border border-black/5">
            <h4 className="font-semibold mb-3">Quick Facts</h4>
            <ul className="space-y-2 text-gray-700">
              <li>• Photorealistic product specialist</li>
              <li>• Full pipeline (modeling → 8K render)</li>
              <li>• Fast iteration & clear communication</li>
              <li>• Open to international opportunities</li>
            </ul>
          </div>
        </div>
      </Section>

      {/* Footer */}
      <footer className="py-10 text-center text-sm text-gray-600">
        © {new Date().getFullYear()} Abdelhadi Laouari — All rights reserved.
      </footer>
    </div>
  );
}
