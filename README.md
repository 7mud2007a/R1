# ForceFieldBackground

A high-performance, interactive particle system background that reacts to mouse movement with a magnetic "force field" effect. Built with p5.js and React.

## Features

- **Interactive Force Field**: Particles disperse as the mouse moves through them.
- **Image-Based Mapping**: Particles are generated based on the brightness map of an underlying image (defaults to a mountain landscape).
- **Dynamic Physics**: Fluid motion with friction and restoration forces.
- **Customizable**: Control hue, saturation, particle density, stroke width, and force field physics.
- **Production Ready**: Responsive canvas resizing, proper React cleanup, and TypeScript support.

## Dependencies

- `p5`: For high-performance canvas rendering
- `react`: Core framework

## Usage

```tsx
import { ForceFieldBackground } from '@/sd-components/febbd3b8-b30b-407b-a997-55442e42be27';

function MyPage() {
  return (
    <div className="relative w-screen h-screen">
      <ForceFieldBackground
        hue={210}
        spacing={10}
        forceStrength={15}
      />

      <div className="absolute inset-0 z-10 flex items-center justify-center pointer-events-none">
        <h1 className="text-white text-6xl font-bold mix-blend-overlay">
          Hello World
        </h1>
      </div>
    </div>
  );
}
```

## Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `imageUrl` | string | (Mountain Image) | Source image URL for particle mapping |
| `hue` | number | 210 | Base color hue (0-360) |
| `saturation` | number | 100 | Color saturation (0-100) |
| `spacing` | number | 10 | Grid spacing (lower = more particles) |
| `density` | number | 2.0 | Random density factor |
| `minStroke` | number | 2 | Minimum particle size |
| `maxStroke` | number | 6 | Maximum particle size |
| `forceStrength` | number | 10 | Strength of cursor repulsion |
| `magnifierRadius` | number | 150 | Radius of interaction area |
| `friction` | number | 0.9 | Movement friction (0.5-0.99) |
| `restoreSpeed` | number | 0.05 | Speed of return to origin |

## Notes

- The component automatically fills its parent container. Ensure the parent has dimensions.
- Mouse interaction is relative to the canvas.
- For best performance, avoid setting `spacing` lower than 5 on large screens.
