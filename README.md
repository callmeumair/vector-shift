# VectorShift Node System

A modern, flexible node system for building AI workflows and applications. This system provides a foundation for creating, styling, and managing nodes in a visual programming interface.

## Features

- 🎨 Modern, unified design system
- 🔄 Dynamic node sizing and layout
- 🎯 Variable detection and handle management
- 🎭 Customizable node types
- 🎮 Interactive node components
- 🎪 Extensible node factory system

## Installation

```bash
# Install dependencies
npm install styled-components reactflow

# Add required fonts
# Add this to your HTML head:
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
```

## Quick Start

```javascript
import { createNode, NodeTypes } from './nodes/BaseNode';
import { TextNode } from './nodes/textNode';

// Create a custom node
const MyCustomNode = createNode({
  type: NodeTypes.CUSTOM,
  title: 'My Node',
  description: 'A custom node example',
  inputs: [{ id: 'input1' }],
  outputs: [{ id: 'output1' }],
  renderContent: ({ data }) => (
    <div>Custom content here</div>
  )
});
```

## Node Types

The system includes several built-in node types:

- **Text Node**: Template-based text with variable support
- **Transform Node**: Text transformation operations
- **Filter Node**: Text filtering and conditions
- **Merge Node**: Combine multiple inputs
- **Split Node**: Split text into multiple outputs
- **Conditional Node**: Route based on conditions

## Styling System

The node system uses a comprehensive theming system with:

- Consistent color palette
- Typography system
- Spacing and sizing scales
- Shadow system
- Node type-specific styling
- Transitions and animations

## Text Node Features

The Text node provides advanced template functionality:

```javascript
// Basic usage
<TextNode text="Hello {{name}}!" />

// Multiple variables
<TextNode text="User {{name}} is {{age}} years old" />

// Dynamic handles
// Creates input handles for 'name' and 'age'
```

### Variable Syntax

- Use `{{variableName}}` to create input handles
- Variables must follow JavaScript naming rules
- Variables are highlighted in the editor
- Handles are created automatically

## Component Structure

```
frontend/src/
├── nodes/
│   ├── BaseNode.js       # Base node component and factory
│   ├── textNode.js       # Text node implementation
│   └── CustomNodes.js    # Additional node types
├── styles/
│   ├── theme.js         # Design system tokens
│   └── NodeStyles.js    # Styled components
└── ...
```

## Creating Custom Nodes

1. Use the node factory:
```javascript
const MyNode = createNode({
  type: NodeTypes.CUSTOM,
  title: 'My Node',
  description: 'Description',
  inputs: [{ id: 'input1' }],
  outputs: [{ id: 'output1' }],
  renderContent: ({ data }) => (
    <div>Content</div>
  )
});
```

2. Style your node:
```javascript
import { NodeContainer, NodeHeader } from '../styles/NodeStyles';

const MyStyledNode = styled(NodeContainer)`
  // Custom styles
`;
```

## Best Practices

1. **Node Design**
   - Keep nodes focused and single-purpose
   - Use clear, descriptive titles
   - Provide helpful descriptions
   - Use appropriate badges for node types

2. **Variable Naming**
   - Use descriptive variable names
   - Follow JavaScript naming conventions
   - Avoid reserved words
   - Keep names concise but clear

3. **Styling**
   - Use theme tokens for consistency
   - Maintain proper spacing
   - Ensure good contrast
   - Support both light and dark themes

4. **Performance**
   - Minimize re-renders
   - Use proper React hooks
   - Optimize large node graphs
   - Handle cleanup properly

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

MIT License - see LICENSE file for details 