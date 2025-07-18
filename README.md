import { Card, CardContent } from "@/components/ui/card";
import { Github, Linkedin } from "lucide-react";
import { motion } from "framer-motion";

export default function Portfolio() {
  return (
    <div className="min-h-screen bg-gradient-to-br from-gray-900 via-black to-gray-800 text-white font-sans">
      <header className="p-8 text-center">
        <motion.h1 
          className="text-4xl md:text-6xl font-bold mb-4"
          initial={{ opacity: 0, y: -20 }} 
          animate={{ opacity: 1, y: 0 }} 
          transition={{ duration: 1 }}>
          Michaela de Bruyn
        </motion.h1>
        <motion.p 
          className="text-lg md:text-xl text-gray-300"
          initial={{ opacity: 0 }} 
          animate={{ opacity: 1 }} 
          transition={{ delay: 0.5 }}>
          Junior Data Scientist | Power BI | SQL | Python
        </motion.p>
        <div className="mt-4 flex justify-center gap-6">
          <a href="https://github.com/Michaela-de-Bruyn" target="_blank" rel="noopener noreferrer"><Github /></a>
          <a href="https://linkedin.com/in/michaela-de-bruyn" target="_blank" rel="noopener noreferrer"><Linkedin /></a>
        </div>
      </header>

      <main className="px-6 md:px-16 py-8 space-y-20">
        <Section title="Skills">
          <div className="grid grid-cols-2 md:grid-cols-4 gap-6">
            {[
              "Python",
              "SQL",
              "Power BI",
              "Excel",
              "Looker Studio",
              "Google Cloud",
              "Data Cleaning",
              "Data Visualization",
              "Statistics",
              "Machine Learning",
              "Data Science Modules",
              "Cloud Tools"
            ].map((skill, index) => (
              <motion.div
                key={index}
                whileHover={{ scale: 1.1 }}
                className="bg-gray-800 p-4 rounded-xl text-center shadow-md border border-gray-700"
              >
                {skill}
              </motion.div>
            ))}
          </div>
        </Section>

        <Section title="Education">
          <Card>
            <CardContent className="p-4 space-y-4">
              <div>
                <h3 className="text-xl font-semibold">Master's in Data Science</h3>
                <p className="text-gray-300">In Progress</p>
              </div>
              <div>
                <h3 className="text-xl font-semibold">Postgraduate Diploma in IT</h3>
                <p className="text-gray-300">Completed</p>
              </div>
              <div>
                <h3 className="text-xl font-semibold">Bachelor of Science in IT</h3>
                <p className="text-gray-300">Graduated Magna Cum Laude</p>
              </div>
            </CardContent>
          </Card>
        </Section>

        <Section title="Contact">
          <p>🌐 github.com/Michaela-de-Bruyn</p>
          <p>🔗 linkedin.com/in/michaela-de-bruyn</p>
        </Section>
      </main>

      <footer className="text-center py-4 text-gray-500 text-sm">
        © 2025 Michaela de Bruyn. All rights reserved.
      </footer>
    </div>
  );
}

function Section({ title, children }) {
  return (
    <motion.section
      className="space-y-4"
      initial={{ opacity: 0, y: 50 }}
      whileInView={{ opacity: 1, y: 0 }}
      transition={{ duration: 0.8 }}
      viewport={{ once: true }}
    >
      <h2 className="text-2xl md:text-3xl font-semibold border-b border-gray-600 pb-2">
        {title}
      </h2>
      {children}
    </motion.section>
  );
}
