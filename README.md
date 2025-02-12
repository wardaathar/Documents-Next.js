# Q-commerce Website

## Overview
This is a modern Food website built with **Next.js, TypeScript, Tailwind CSS, Shadcn Sheet, and React**. The project includes a **dynamic shopping cart** and is deployed on **Vercel**.

## Features
- **Dynamic Data Fetching** via APIs
- **Shopping Cart Functionality** (Add/Remove Items)
- **Type-safe Code** with TypeScript
- **Shadcn Sheet** for UI Components
- **Custom Hooks** for State Management
- **Responsive Design** with Tailwind CSS
- **Static & Dynamic Routes**
- **Deployment on Vercel**

## Installation
### Clone the repository:
```bash
git clone https://github.com/your-username/ecommerce-website.git
cd ecommerce-website
```

### Install dependencies:
```bash
npm install
```

### Create a `.env.local` file in the root directory and add your environment variables:
```plaintext
NEXT_PUBLIC_API_URL=your_api_url
```

### Run the development server:
```bash
npm run dev
```

### Open your browser and visit:
```
http://localhost:3000
```

## Usage

### Hooks
The project uses custom hooks for state management and side effects. Here are some examples:

#### `useCart`: Manages the state of the shopping cart.
```tsx
import { useState } from 'react';

export const useCart = () => {
  const [cart, setCart] = useState([]);

  const addItem = (item) => {
    setCart([...cart, item]);
  };

  const removeItem = (itemId) => {
    setCart(cart.filter(item => item.id !== itemId));
  };

  return { cart, addItem, removeItem };
};
```

#### `useFetch`: Fetches data from an API.
```tsx
import { useState, useEffect } from 'react';

export const useFetch = (url: string) => {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await fetch(url);
        const result = await response.json();
        setData(result);
      } catch (err) {
        setError(err);
      } finally {
        setLoading(false);
      }
    };
    fetchData();
  }, [url]);

  return { data, loading, error };
};
```

## Deployment
To deploy the project on Vercel, run the following command:
```bash
https://hackhton-ui-ux-assignment.vercel.app
```

---

**Happy Coding! 🚀**
