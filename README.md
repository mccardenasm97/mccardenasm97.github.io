import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { CountdownCircleTimer } from "react-countdown-circle-timer";
import { motion } from "framer-motion";

export default function BirthdayPage() {
  const birthdayDate = new Date("2025-02-14"); // Cambia a la fecha del cumpleaños
  const timeUntilBirthday = Math.max(0, (birthdayDate - new Date()) / 1000);

  return (
    <div className="min-h-screen bg-gradient-to-r from-pink-300 via-purple-300 to-pink-300 p-4 text-center">
      <header className="mb-6">
        <motion.h1
          className="text-4xl font-bold text-white drop-shadow-lg"
          initial={{ y: -50, opacity: 0 }}
          animate={{ y: 0, opacity: 1 }}
          transition={{ duration: 0.8 }}
        >
          ¡Feliz Cumpleaños, Amor!
        </motion.h1>
        <motion.p
          className="text-lg text-white mt-2"
          initial={{ opacity: 0 }}
          animate={{ opacity: 1 }}
          transition={{ duration: 1.2 }}
        >
          Esta página está dedicada a ti con todo mi amor 💖
        </motion.p>
      </header>

      {/* Contador regresivo */}
      <div className="flex justify-center mb-6">
        <CountdownCircleTimer
          isPlaying
          duration={timeUntilBirthday}
          colors={["#D14081", "#EF798A", "#EA5455"]}
          colorsTime={[7, 5, 2, 0]}
        >
          {({ remainingTime }) => (
            <div className="text-white text-2xl">
              {remainingTime > 0
                ? ${Math.floor(remainingTime / 86400)} días restantes
                : "¡Feliz Cumpleaños! 🎉"}
            </div>
          )}
        </CountdownCircleTimer>
      </div>

      {/* Mensaje especial */}
      <Card className="mb-6 bg-white/90 shadow-lg">
        <CardContent>
          <p className="text-gray-800 text-lg">
            Querida [nombre de tu novia],
            <br />
            Hoy celebro no solo tu cumpleaños, sino también la dicha de tenerte
            en mi vida. Eres mi alegría, mi paz y mi inspiración. Te amo más de
            lo que las palabras pueden expresar. 💕
          </p>
        </CardContent>
      </Card>

      {/* Galería de fotos */}
      <section className="mb-6">
        <h2 className="text-2xl font-bold text-white mb-4">Nuestros Recuerdos</h2>
        <div className="grid grid-cols-2 gap-4">
          <img
            src="/images/photo1.jpg"
            alt="Recuerdo 1"
            className="rounded-lg shadow-lg"
          />
          <img
            src="/images/photo2.jpg"
            alt="Recuerdo 2"
            className="rounded-lg shadow-lg"
          />
          <img
            src="/images/photo3.jpg"
            alt="Recuerdo 3"
            className="rounded-lg shadow-lg"
          />
          <img
            src="/images/photo4.jpg"
            alt="Recuerdo 4"
            className="rounded-lg shadow-lg"
          />
        </div>
      </section>

      {/* Cronología de recuerdos */}
      <section className="mb-6">
        <h2 className="text-2xl font-bold text-white mb-4">Nuestra Historia</h2>
        <ul className="text-white text-lg space-y-2">
          <li>🌟 Primer encuentro: [fecha y descripción]</li>
          <li>🌹 Primer "Te amo": [fecha y descripción]</li>
          <li>🎉 Aventuras memorables: [descripción breve]</li>
        </ul>
      </section>

      {/* Video dedicado */}
      <section className="mb-6">
        <h2 className="text-2xl font-bold text-white mb-4">Video Especial</h2>
        <video
          controls
          className="w-full max-w-lg mx-auto rounded-lg shadow-lg"
        >
          <source src="/videos/birthday-video.mp4" type="video/mp4" />
          Tu navegador no soporta la reproducción de video.
        </video>
      </section>

      {/* Formulario de mensajes */}
      <section>
        <h2 className="text-2xl font-bold text-white mb-4">
          Mensajes de tus seres queridos
        </h2>
        <form className="bg-white p-4 rounded-lg shadow-lg">
          <textarea
            placeholder="Escribe tu mensaje..."
            className="w-full h-20 p-2 border border-gray-300 rounded-lg mb-2"
          ></textarea>
          <Button type="submit">Enviar</Button>
        </form>
      </section>
    </div>
  );
}
