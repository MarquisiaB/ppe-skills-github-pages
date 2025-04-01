---
title: Precious-Productions-ent.
---

export const config = {
  homepage: "https://PreciousProductions.ent.github.io/PreciousProductions.ent.github.io",
  scripts: {
    predeploy: "npm run build",
    deploy: "gh-pages -d build",
  },
};
import React, { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { motion } from "framer-motion";

const comedySpecials = [
  {
    title: "Laugh Riot Night",
    description: "A night of non-stop laughter featuring top comedians!",
    date: "June 13, 2025",
    time: "4:00pm",
    location: "Kentland Baptist Church",
  },
  {
    title: "Comedy Kings & Queens",
    description: "Stand-up comedy at its finest! Don't miss out.",
    date: "June 14, 2025",
    time: "Doors open at 7:30pm, Show starts at 8:00pm",
    location: "B&G Tavern",
  },
  {
    title: "Jokes on You Tour",
    description: "A hilarious tour across major cities!",
    date: "June 10, 2025",
    time: "TBA",
    location: "Chicago Laugh Arena, IL",
  },
];

export default function ComedySpecials() {
  const [openEvent, setOpenEvent] = useState(null);
  const [activePage, setActivePage] = useState("Home");

  const toggleEvent = (index) => {
    setOpenEvent(openEvent === index ? null : index);
  };

  return (
    <div className="flex min-h-screen bg-gray-900 text-white">
      {/* Sidebar Navigation */}
      <div className="w-64 bg-gray-800 p-6">
        <h2 className="text-2xl font-bold mb-6">Menu</h2>
        <ul className="space-y-4">
          <li><button className="w-full text-left" onClick={() => setActivePage("Home")}>Home</button></li>
          <li><button className="w-full text-left" onClick={() => setActivePage("Upcoming Shows")}>Upcoming Shows</button></li>
          <li><button className="w-full text-left" onClick={() => setActivePage("Fan Favorites/Highlights")}>Fan Favorites/Highlights</button></li>
          <li><button className="w-full text-left" onClick={() => setActivePage("About Us")}>About Us</button></li>
          <li><button className="w-full text-left" onClick={() => setActivePage("Contact")}>Contact</button></li>
        </ul>
      </div>

      {/* Main Content */}
      <div className="flex-1 p-6">
        {activePage === "Home" && (
          <div>
            <motion.h1 className="text-3xl font-bold text-center mb-6" initial={{ opacity: 0, y: -20 }} animate={{ opacity: 1, y: 0 }}>
              Welcome to Precious Productions Ent.
            </motion.h1>
            <p className="text-center mb-8 max-w-2xl mx-auto">
              Your premier destination for top-tier comedy entertainment. We bring you the best comedians
              from around the country to deliver unforgettable nights of laughter.
            </p>
          </div>
        )}

        {activePage === "Upcoming Shows" && (
          <div className="max-w-3xl mx-auto">
            <motion.h2 className="text-2xl font-bold text-center mb-6" initial={{ opacity: 0 }} animate={{ opacity: 1 }}>
              Upcoming Comedy Specials
            </motion.h2>
            {comedySpecials.map((special, index) => (
              <div key={index} className="mb-4">
                <button className="w-full text-left bg-gray-800 p-4 rounded-lg shadow-md focus:outline-none" onClick={() => toggleEvent(index)}>
                  <span className="text-lg font-semibold">{special.title}</span>
                </button>
                {openEvent === index && (
                  <motion.div className="mt-2 bg-gray-700 p-4 rounded-lg" initial={{ opacity: 0, height: 0 }} animate={{ opacity: 1, height: "auto" }}>
                    <CardContent>
                      <p className="mb-2">{special.description}</p>
                      <p className="text-sm text-gray-400">📅 {special.date}</p>
                      <p className="text-sm text-gray-400">⏰ {special.time}</p>
                      <p className="text-sm text-gray-400">📍 {special.location}</p>
                      <Button className="mt-4 bg-red-500 hover:bg-red-600">Get Tickets</Button>
                    </CardContent>
                  </motion.div>
                )}
              </div>
            ))}
          </div>
        )}

        {activePage === "Fan Favorites/Highlights" && (
          <div className="text-center">
            <motion.h2 className="text-2xl font-bold mb-6" initial={{ opacity: 0 }} animate={{ opacity: 1 }}>
              Fan Favorites & Highlights
            </motion.h2>
            <p className="max-w-2xl mx-auto">
              Check out the most loved moments and top performances from our past comedy specials! Stay tuned for updates.
            </p>
          </div>
        )}

        {activePage === "About Us" && (
          <div className="text-center">
            <motion.h2 className="text-2xl font-bold mb-6" initial={{ opacity: 0 }} animate={{ opacity: 1 }}>
              About Us
            </motion.h2>
            <p className="max-w-2xl mx-auto">
              Precious Productions Ent. is dedicated to bringing the best comedy entertainment to audiences nationwide. 
              Our mission is to create unforgettable experiences filled with laughter, joy, and the best comedic talent.
            </p>
          </div>
        )}

        {activePage === "Contact" && (
          <div className="text-center">
            <motion.h2 className="text-2xl font-bold mb-6" initial={{ opacity: 0 }} animate={{ opacity: 1 }}>
              Contact Us
            </motion.h2>
            <p className="max-w-2xl mx-auto">
              Have questions or want to get in touch? Email us at contact@preciousproductions.com or call (123) 456-7890.
            </p>
          </div>
        )}
      </div>
    </div>
  );
}
// package.json configuration
export const config = {
  homepage: "https://Precious.ProductionsENT.github.io./Precious.ProductionsENT.github.io",
  scripts: {
    predeploy: "npm run build",
    deploy: "gh-pages -d build",
  },
};

// Debugger configuration
export const debugConfig = {
  version: "0.2.0",
  configurations: [
    {
      type: "node",
      name: "Run Current File",
      request: "launch",
      program: "${workspaceFolder}\\react.js",
    },
  ],
};{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version"; "0.2.0",
  "configurations"; [
      
      {
          "name": "Launch Edge",
          "request": "launch",
          "type": "msedge",
          "url": "http://localhost:8080",
          "webRoot": "${workspaceFolder}"
      },
      {
          "name": "Attach to Edge",
          "port": 9222,
          "request": "attach",
          "type": "msedge",
          "webRoot": "${workspaceFolder}"
      },
      {
          "name": "Launch Chrome",
          "request": "launch",
          "type": "chrome",
          "url": "http://localhost:8080",
          "webRoot": "${workspaceFolder}"
      },
      {
          "name": "Attach to Chrome",
          "port": 9222,
          "request": "attach",
          "type": "chrome",
          "webRoot": "${workspaceFolder}"
      },
      {
          "name": "Launch via NPM",
          "request": "launch",
          "runtimeArgs": [
              "run-script",
              "debug"
          ],
          "runtimeExecutable": "npm",
          "skipFiles": [
              "<node_internals>/**"
          ],
          "type": "node"
      },
      
      {
          "type": "node",
          "name": "Run Current File",
          "request": "launch",
          "program": "${workspaceFolder}\\react.js"
      }
  ]
}
git clone
