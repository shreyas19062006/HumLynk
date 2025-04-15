import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { motion } from "framer-motion";
import { Mail, Users, Globe2, Megaphone, Star, CheckCircle } from "lucide-react";

const features = [
  {
    icon: <Users className="h-8 w-8 text-primary" />,
    title: "Community-Powered Outreach",
    description:
      "HumLynk leverages student-led micro-teams to build organic, human-centric campaigns across platforms."
  },
  {
    icon: <Globe2 className="h-8 w-8 text-primary" />,
    title: "Global Social Media Marketing",
    description:
      "We manage your brand across all major platforms including LinkedIn, Instagram, X, and more."
  },
  {
    icon: <Megaphone className="h-8 w-8 text-primary" />,
    title: "Lead Generation with a Human Touch",
    description:
      "We build genuine conversations that convert. No bots, no automation—just real people."
  },
  {
    icon: <Mail className="h-8 w-8 text-primary" />,
    title: "Strategic Partnerships",
    description:
      "We collaborate with digital media firms and agencies for long-term growth and co-branded campaigns."
  }
];

const testimonials = [
  {
    name: "Priya Sharma",
    feedback: "HumLynk helped us grow our LinkedIn reach organically and connected us with the right people. Real humans, real impact!"
  },
  {
    name: "David Kim",
    feedback: "Their community-first approach is refreshing. We’ve seen a 3x improvement in engagement in just 2 months."
  }
];

const pricing = [
  {
    plan: "Starter",
    price: "$299/mo",
    features: ["Platform-specific strategy", "1 micro-pod", "Weekly performance updates"]
  },
  {
    plan: "Pro",
    price: "$699/mo",
    features: ["Multi-platform marketing", "3 micro-pods", "Lead nurturing & reporting"]
  },
  {
    plan: "Enterprise",
    price: "Custom",
    features: ["Tailored outreach", "Unlimited micro-pods", "Strategic consulting & scaling"]
  }
];

export default function Home() {
  return (
    <div className="min-h-screen bg-white text-gray-800 px-4 sm:px-8 py-8">
      <motion.div
        initial={{ opacity: 0, y: -20 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.8 }}
        className="text-center mb-12"
      >
        <h1 className="text-4xl sm:text-6xl font-bold mb-2 text-primary">
          HumLynk
        </h1>
        <p className="text-xl sm:text-2xl font-medium text-red-500">
          Launching Soon 🚀
        </p>
        <p className="text-lg sm:text-xl text-gray-600 max-w-2xl mx-auto mt-4">
          A human-powered marketing and lead generation agency helping brands grow through meaningful community engagement.
        </p>
        <Button className="mt-6">Join Our Waitlist</Button>
      </motion.div>

      <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
        {features.map((feature, index) => (
          <Card key={index} className="rounded-2xl shadow-md">
            <CardContent className="p-6 flex flex-col items-center text-center">
              {feature.icon}
              <h3 className="text-xl font-semibold mt-4 mb-2">{feature.title}</h3>
              <p className="text-sm text-gray-600">{feature.description}</p>
            </CardContent>
          </Card>
        ))}
      </div>

      <div className="mt-20 text-center max-w-3xl mx-auto">
        <h2 className="text-3xl font-bold mb-4">Why Choose HumLynk?</h2>
        <p className="text-md text-gray-700">
          Unlike traditional agencies, we blend the energy of student talent with the strategy of experienced marketers. We don't just automate outreach—we build human connections that foster loyalty and drive real results.
        </p>
      </div>

      <div className="mt-20">
        <h3 className="text-2xl font-bold text-center mb-6">What Our Clients Say</h3>
        <div className="grid sm:grid-cols-2 gap-6">
          {testimonials.map((item, index) => (
            <Card key={index} className="rounded-xl shadow-sm">
              <CardContent className="p-6">
                <p className="text-gray-700 italic">“{item.feedback}”</p>
                <p className="text-sm text-right mt-4 font-semibold">- {item.name}</p>
              </CardContent>
            </Card>
          ))}
        </div>
      </div>

      <div className="mt-20 text-center">
        <h3 className="text-3xl font-bold mb-6">Simple Pricing</h3>
        <div className="grid sm:grid-cols-3 gap-6">
          {pricing.map((tier, index) => (
            <Card key={index} className="rounded-xl shadow-md">
              <CardContent className="p-6 text-center">
                <h4 className="text-xl font-semibold mb-2">{tier.plan}</h4>
                <p className="text-2xl font-bold text-primary mb-4">{tier.price}</p>
                <ul className="text-sm text-gray-700 space-y-2">
                  {tier.features.map((feat, i) => (
                    <li key={i} className="flex items-center justify-center gap-2">
                      <CheckCircle className="h-4 w-4 text-green-500" /> {feat}
                    </li>
                  ))}
                </ul>
              </CardContent>
            </Card>
          ))}
        </div>
      </div>

      <div className="mt-20 text-center">
        <h3 className="text-2xl font-semibold mb-4">Let’s Build Something Together</h3>
        <p className="text-gray-600 mb-6">Contact us to collaborate or learn more about how HumLynk can grow your brand.</p>
        <Button variant="outline">Contact Us</Button>
      </div>
    </div>
  );
}
