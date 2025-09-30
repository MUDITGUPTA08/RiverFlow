# RiverFlow AI - Image Generator

A beautiful, modern web application for AI-powered image generation built with Next.js, TypeScript, and Tailwind CSS.

![RiverFlow AI](https://img.shields.io/badge/Next.js-15.5.4-black?style=for-the-badge&logo=next.js)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue?style=for-the-badge&logo=typescript)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4.0-38B2AC?style=for-the-badge&logo=tailwind-css)

## ✨ Features

- 🎨 **AI Image Generation** - Generate stunning images from text prompts
- 🎯 **Modern UI/UX** - Beautiful gradient design with glassmorphism effects
- 📱 **Responsive Design** - Works perfectly on desktop and mobile devices
- ⚡ **Real-time Generation** - Fast image generation with loading states
- 💾 **Download Images** - Save generated images to your device
- 🎭 **Example Prompts** - Get started with pre-written prompt suggestions
- 🔄 **Error Handling** - Comprehensive error handling and user feedback

## 🚀 Getting Started

### Prerequisites

- Node.js 18.0 or later
- npm, yarn, pnpm, or bun

### Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd riverflow
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   # or
   pnpm install
   ```

3. **Run the development server**
   ```bash
   npm run dev
   # or
   yarn dev
   # or
   pnpm dev
   ```

4. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

## 🤖 AI Service Integration

Currently, the app uses mock image generation for demonstration purposes. To integrate with real AI services, follow these steps:

### Option 1: OpenAI DALL-E

1. **Get an API key** from [OpenAI](https://platform.openai.com/api-keys)

2. **Install the OpenAI package**
   ```bash
   npm install openai
   ```

3. **Create environment variables**
   ```bash
   # .env.local
   OPENAI_API_KEY=your_openai_api_key_here
   ```

4. **Update the API route** in `app/api/generate-image/route.ts`:
   ```typescript
   import OpenAI from 'openai';
   
   const openai = new OpenAI({
     apiKey: process.env.OPENAI_API_KEY,
   });
   
   // Replace the mock function with:
   async function generateWithOpenAI(prompt: string): Promise<string> {
     const response = await openai.images.generate({
       model: "dall-e-3",
       prompt: prompt,
       n: 1,
       size: "1024x1024",
       quality: "standard",
     });
     return response.data[0].url;
   }
   ```

### Option 2: Stability AI

1. **Get an API key** from [Stability AI](https://platform.stability.ai/account/keys)

2. **Create environment variables**
   ```bash
   # .env.local
   STABILITY_API_KEY=your_stability_api_key_here
   ```

3. **Update the API route** to use Stability AI (see commented code in the API file)

### Option 3: Replicate

1. **Get an API key** from [Replicate](https://replicate.com/account/api-tokens)

2. **Install the Replicate package**
   ```bash
   npm install replicate
   ```

3. **Create environment variables**
   ```bash
   # .env.local
   REPLICATE_API_TOKEN=your_replicate_token_here
   ```

## 🎨 Customization

### Styling
The app uses Tailwind CSS with custom gradients and glassmorphism effects. You can customize the colors in:
- `app/page.tsx` - Main component styling
- `app/globals.css` - Global styles

### Features
- Add image size options
- Implement image history/persistence
- Add image editing capabilities
- Implement user accounts and galleries

## 📁 Project Structure

```
riverflow/
├── app/
│   ├── api/
│   │   └── generate-image/
│   │       └── route.ts          # API endpoint for image generation
│   ├── globals.css               # Global styles
│   ├── layout.tsx                # Root layout component
│   └── page.tsx                  # Main page component
├── public/                       # Static assets
├── package.json                  # Dependencies and scripts
└── README.md                     # This file
```

## 🛠️ Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint

## 🚀 Deployment

### Deploy to Vercel (Recommended)

1. **Push your code** to GitHub
2. **Import your repository** to [Vercel](https://vercel.com/new)
3. **Add environment variables** in Vercel dashboard
4. **Deploy!**

### Deploy to Other Platforms

The app can be deployed to any platform that supports Next.js:
- Netlify
- Railway
- DigitalOcean App Platform
- AWS Amplify

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Next.js](https://nextjs.org/) - The React framework
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- [OpenAI](https://openai.com/) - AI image generation capabilities
- [Vercel](https://vercel.com/) - Deployment platform

---

**Note**: This application currently uses mock image generation for demonstration. To generate real AI images, you'll need to integrate with one of the supported AI services and provide valid API keys.
