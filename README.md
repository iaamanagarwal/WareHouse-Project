# Warehouse Dashboard

A modern, responsive warehouse automation dashboard built with React, Tailwind CSS, and Framer Motion. This application provides real-time monitoring and management of warehouse robots, tasks, and inventory with beautiful visualizations and smooth animations.

![Warehouse Dashboard](https://via.placeholder.com/800x400/3b82f6/ffffff?text=Warehouse+Dashboard)

## Features

### 🤖 Robot Management
- Real-time robot status monitoring (Idle, Busy, Charging)
- Battery level visualization with progress bars
- Location tracking across warehouse zones
- Interactive status distribution charts
- Search and filter capabilities
- Responsive card-based layout

### 📋 Task Management
- Create and assign tasks to available robots
- Track task status (Pending, In-progress, Completed)
- Task priority management (High, Medium, Low)
- Route visualization (source → destination)
- Active/completed task tabs
- Real-time task updates

### 📦 Inventory Management
- Comprehensive inventory tracking
- Low stock alerts and highlighting
- Category-based filtering and sorting
- Stock distribution visualizations
- Search and pagination
- Value calculations

### 🎨 Bonus Features
- **2D Warehouse Map**: Interactive floor plan showing robot and inventory locations
- **3D Visualization**: Three.js-powered 3D view of warehouse robots
- **Dark/Light Mode**: Persistent theme switching
- **Smooth Animations**: Framer Motion-powered transitions
- **Responsive Design**: Mobile-first, fully responsive layouts

## Tech Stack

- **Frontend Framework**: React 18+ (functional components, hooks)
- **Styling**: Tailwind CSS with custom design system
- **State Management**: Zustand for global state
- **Routing**: React Router v6
- **Charts**: Recharts for data visualization
- **Animations**: Framer Motion for smooth transitions
- **3D Graphics**: Three.js with React Three Fiber
- **Icons**: Lucide React
- **Build Tool**: Vite
- **Container**: Docker with multi-stage builds

## Project Structure

```
src/
├── components/
│   ├── common/            # Reusable UI components
│   │   ├── Card.jsx
│   │   ├── StatusChip.jsx
│   │   ├── SearchInput.jsx
│   │   ├── Pagination.jsx
│   │   ├── Badge.jsx
│   │   └── Modal.jsx
│   ├── layout/            # Layout components
│   │   ├── Header.jsx
│   │   ├── Sidebar.jsx
│   │   └── PageContainer.jsx
│   ├── robots/            # Robot-specific components
│   │   ├── RobotCard.jsx
│   │   └── RobotStatusBarChart.jsx
│   ├── tasks/             # Task-specific components
│   │   ├── TaskList.jsx
│   │   └── TaskForm.jsx
│   ├── inventory/         # Inventory-specific components
│   │   ├── InventoryTable.jsx
│   │   └── InventoryChart.jsx
│   └── warehouse/         # Warehouse visualization
│       ├── WarehouseMap.jsx
│       └── Warehouse3DView.jsx
├── pages/                 # Main page components
│   ├── RobotsPage.jsx
│   ├── TasksPage.jsx
│   └── InventoryPage.jsx
├── store/                 # State management
│   └── useWarehouseStore.js
├── data/                  # Mock data
│   ├── robotsMock.js
│   ├── tasksMock.js
│   └── inventoryMock.js
└── utils/                 # Utility functions
```

## Quick Start

### Prerequisites
- Node.js 18+ 
- npm or yarn

### Installation

1. **Clone and install dependencies:**
   ```bash
   npm install
   ```

2. **Start development server:**
   ```bash
   npm run dev
   ```

3. **Open in browser:**
   Navigate to [http://localhost:3000](http://localhost:3000)

### Production Build

```bash
# Build for production
npm run build

# Preview production build
npm run preview
```

## Docker Deployment

### Quick Start with Docker

```bash
# Build and run production container
docker build -t warehouse-dashboard .
docker run -p 3000:80 warehouse-dashboard
```

### Using Docker Compose

```bash
# Production deployment
docker-compose up

# Development with hot reload
docker-compose --profile dev up warehouse-dashboard-dev
```

The application will be available at:
- **Production**: [http://localhost:3000](http://localhost:3000)
- **Development**: [http://localhost:3001](http://localhost:3001)

## Usage Guide

### Navigation
Use the sidebar to navigate between:
- **Robots**: Monitor robot status, battery, and locations
- **Tasks**: Create and manage warehouse tasks
- **Inventory**: Track stock levels and manage items

### Key Features

#### Robot Management
- View all robots in a responsive grid layout
- Filter by status (All, Idle, Busy, Charging)
- Search by robot ID, name, or location
- Click robots on the 2D map to highlight them
- Monitor battery levels with visual progress bars

#### Task Creation
1. Click "Create Task" button
2. Select item from inventory dropdown
3. Choose source and destination locations
4. Optionally assign to an available robot
5. Set priority level
6. Submit to create the task

#### Inventory Monitoring
- Sort by any column (name, quantity, location, etc.)
- Filter by category or low stock status
- View distribution charts by category
- Monitor stock levels and receive low stock alerts

### Dark Mode
Toggle between light and dark themes using the moon/sun icon in the header. Your preference is automatically saved.

## API Integration

This is a frontend-only application using mock data. To connect to a real backend:

1. **Replace mock data** in `src/data/` with API calls
2. **Update store actions** in `src/store/useWarehouseStore.js`
3. **Add API client** (axios, fetch, etc.)
4. **Handle loading states** and error handling

Example API integration:
```javascript
// In useWarehouseStore.js
const fetchRobots = async () => {
  try {
    const response = await fetch('/api/robots')
    const robots = await response.json()
    set({ robots })
  } catch (error) {
    console.error('Failed to fetch robots:', error)
  }
}
```

## Customization

### Styling
- Modify colors in `tailwind.config.js`
- Update design tokens in `src/index.css`
- Customize component styles using Tailwind classes

### Adding Features
- Create new components in appropriate folders
- Update the store for state management
- Add routes in `src/App.jsx`
- Follow existing patterns for consistency

## Performance

The application is optimized for performance:
- **Code splitting** with React.lazy (can be added)
- **Efficient re-renders** with proper state management
- **Optimized builds** with Vite
- **Responsive images** and assets
- **Gzip compression** in production

## Browser Support

- Chrome (latest)
- Firefox (latest) 
- Safari (latest)
- Edge (latest)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

MIT License - see LICENSE file for details.

## Support

For questions or support:
- Create an issue on GitHub
- Check the documentation in `/docs`
- Review the design document for architecture details

---

**Built with ❤️ using React, Tailwind CSS, and modern web technologies.**