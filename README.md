/*
  GitHub Portfolio - Single-file React component
  Usage:
  1. Create a React app (Vite / Create React App).
  2. Install Tailwind CSS and configure it.
  3. Save this file as `src/components/PortfolioPage.jsx`.
  4. Import and render <PortfolioPage /> from App.jsx or your router.

  This component is intentionally self-contained and uses Tailwind classes.
  Replace data in the `profile` and `projects` arrays with your real info.
*/

import React from "react";

const profile = {
  name: "Manish Sharma",
  role: "PPC Engineer — Production Management",
  location: "India",
  bio: "I design efficient production flows, manage BOM cost analysis and create automation in Excel & SAP MM (S4/HANA).",
  avatar: "https://avatars.githubusercontent.com/identicon?size=128&name=ManishSharma",
  socials: [
    { name: "GitHub", href: "https://github.com/your-username" },
    { name: "LinkedIn", href: "https://linkedin.com/in/your-username" },
    { name: "Email", href: "mailto:your.email@example.com" },
  ],
};

const projects = [
  {
    id: 1,
    title: "Production BOM Analyzer",
    desc: "Excel + Python tool to parse BOMs, summarize variances and generate cost reports.",
    tech: ["Excel", "Python", "Pandas"],
    href: "https://github.com/your-username/bom-analyzer",
  },
  {
    id: 2,
    title: "MS-Office Automation Templates",
    desc: "A collection of Excel & PowerPoint templates and macros (VBA) used across production teams.",
    tech: ["VBA", "Excel", "PowerPoint"],
    href: "https://github.com/your-username/ms-office-templates",
  },
  {
    id: 3,
    title: "SAP MM S4/HANA Samples",
    desc: "Documentation and step-by-step guides for common SAP MM S4/HANA scenarios used in manufacturing.",
    tech: ["SAP S4/HANA", "Documentation"],
    href: "https://github.com/your-username/sap-mm-examples",
  },
];

export default function PortfolioPage() {
  return (
    <div className="min-h-screen bg-slate-50 text-slate-800">
      <header className="max-w-5xl mx-auto p-6 flex items-center justify-between">
        <div className="flex items-center gap-4">
          <img src={profile.avatar} alt="avatar" className="w-12 h-12 rounded-full ring-2 ring-slate-200" />
          <div>
            <h1 className="text-lg font-semibold">{profile.name}</h1>
            <p className="text-sm text-slate-500">{profile.role}</p>
          </div>
        </div>
        <nav className="hidden md:flex gap-6 text-sm text-slate-600">
          <a href="#projects" className="hover:underline">Projects</a>
          <a href="#about" className="hover:underline">About</a>
          <a href="#contact" className="hover:underline">Contact</a>
          <a
            href={profile.socials[0].href}
            className="px-3 py-1 border rounded-md text-sm hover:bg-slate-100"
            target="_blank"
            rel="noreferrer"
          >
            View GitHub
          </a>
        </nav>
        <button className="md:hidden p-2 rounded-md bg-white ring-1 ring-slate-200">☰</button>
      </header>

      <main className="max-w-5xl mx-auto p-6">
        <section className="grid grid-cols-1 md:grid-cols-3 gap-6 items-center bg-white rounded-2xl p-6 shadow-sm">
          <div className="md:col-span-2">
            <h2 className="text-3xl font-extrabold leading-tight">Hi — I'm {profile.name}.</h2>
            <p className="mt-3 text-slate-600">{profile.bio}</p>

            <div className="mt-6 flex flex-wrap gap-3">
              <a
                href={profile.socials[0].href}
                className="inline-flex items-center gap-2 px-4 py-2 bg-slate-800 text-white rounded-lg text-sm"
                target="_blank"
                rel="noreferrer"
              >
                View GitHub ↗
              </a>
              <a href="#projects" className="inline-flex items-center gap-2 px-4 py-2 border rounded-lg text-sm">
                See projects
              </a>
            </div>

            <div className="mt-6 grid grid-cols-2 sm:grid-cols-3 gap-3 text-sm text-slate-600">
              <div className="p-3 bg-slate-50 rounded-lg">SAP MM (S4/HANA)</div>
              <div className="p-3 bg-slate-50 rounded-lg">Excel Expert (VLOOKUP, INDEX/MATCH)</div>
              <div className="p-3 bg-slate-50 rounded-lg">BOM Cost Management</div>
              <div className="p-3 bg-slate-50 rounded-lg">Production Planning</div>
              <div className="p-3 bg-slate-50 rounded-lg">Power BI / Reporting</div>
              <div className="p-3 bg-slate-50 rounded-lg">Critical Thinking</div>
            </div>
          </div>

          <aside className="flex flex-col items-center gap-3">
            <img src={profile.avatar} alt="avatar large" className="w-36 h-36 rounded-xl ring-2 ring-slate-100" />
            <p className="text-sm text-slate-500">{profile.location}</p>
            <div className="flex gap-2">
              {profile.socials.map((s) => (
                <a key={s.name} href={s.href} target="_blank" rel="noreferrer" className="text-sm underline">
                  {s.name}
                </a>
              ))}
            </div>
          </aside>
        </section>

        <section id="projects" className="mt-10">
          <h3 className="text-2xl font-bold">Projects</h3>
          <p className="text-slate-600 mt-2">Selected projects — full repos linked to GitHub.</p>

          <div className="mt-6 grid grid-cols-1 md:grid-cols-3 gap-6">
            {projects.map((p) => (
              <article key={p.id} className="bg-white rounded-2xl p-5 shadow-sm hover:shadow-md transition">
