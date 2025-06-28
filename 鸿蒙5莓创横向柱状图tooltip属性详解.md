### Hello and welcome back to our special session on HarmonyOS 5 Berry Creative chart components. In this episode, we'll explore the detailed usage of the **tooltip** properties in the horizontal bar chart (McHorBarChart). The tooltip is a crucial interactive component that displays detailed data when users hover over or click on chart elements. Let's dive into each tooltip property and its sub-properties.  


### 1. `show` Property  
**Function**: Toggles tooltip visibility.  
**Type**: Boolean  
**Default**: `true`  
**Options**: `true` (show) / `false` (hide)  
**Scenario**: Disable tooltips for small mobile charts or when unnecessary.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    show: false // Disable tooltip entirely
  },
  // Other configurations...
})
```  


### 2. `padding` Property  
**Function**: Sets internal padding of the tooltip.  
**Type**: Number  
**Default**: 10  
**Scenario**: Increase for dense content or decrease for compact layouts.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    padding: 15 // Larger internal padding
  },
  // Other configurations...
})
```  


### 3. `backgroundColor` Property  
**Function**: Sets tooltip background color.  
**Type**: String  
**Default**: `'rgba(0,0,0,0.7)'`  
**Scenario**: Match the app theme for consistency and readability.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    backgroundColor: 'rgba(255,255,255,0.9)' // Semi-transparent white background
  },
  // Other configurations...
})
```  


### 4. `borderWidth` Property  
**Function**: Sets tooltip border width.  
**Type**: Number  
**Default**: 0  
**Scenario**: Highlight the tooltip boundary.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    borderWidth: 1 // 1px border
  },
  // Other configurations...
})
```  


### 5. `borderColor` Property  
**Function**: Sets tooltip border color.  
**Type**: String  
**Default**: `'rgba(0,0,0,0.7)'`  
**Scenario**: Customize border color with `borderWidth`.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    borderWidth: 1,
    borderColor: '#ff2659f5' // Pink border
  },
  // Other configurations...
})
```  


### 6. `axisPointer` Property  
**Function**: Configures indicator line style (line or shadow).  
**Type**: Object  
**Scenario**: Highlight the coordinate position of the current data item.  

#### 6.1 `type` Sub-property  
**Function**: Sets indicator type.  
**Type**: String  
**Default**: `'line'`  
**Options**: `'line'` (linear) / `'shadow'` (shadow)  
**Scenario**: Use `line` for precise indication or `shadow` for range emphasis.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      type: 'shadow' // Use shadow indicator
    }
  },
  // Other configurations...
})
```  


#### 6.2 `lineStyle` Sub-property  
**Function**: Configures linear indicator style.  
**Type**: Object  

##### 6.2.1 `width` Sub-property  
**Function**: Sets line width.  
**Type**: Number  
**Default**: 1  
**Scenario**: Adjust indicator thickness.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      lineStyle: {
        width: 2 // Thicker indicator
      }
    }
  },
  // Other configurations...
})
```  


##### 6.2.2 `type` Sub-property  
**Function**: Sets line style.  
**Type**: String  
**Default**: `'solid'`  
**Options**: `'solid'` / `'dashed'` / `'dotted'`  
**Scenario**: Use dashed/dotted lines for softer visual indication.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      lineStyle: {
        type: 'dashed' // Dashed indicator
      }
    }
  },
  // Other configurations...
})
```  


##### 6.2.3 `color` Sub-property  
**Function**: Sets line color.  
**Type**: String  
**Default**: `'#DDE2EB'`  
**Scenario**: Match indicator color to the chart theme.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      lineStyle: {
        color: '#ff2659f5' // Pink indicator
      }
    }
  },
  // Other configurations...
})
```  


#### 6.3 `shadowStyle` Sub-property  
**Function**: Configures shadow indicator style.  
**Type**: Object  

##### 6.3.1 `color` Sub-property  
**Function**: Sets shadow color.  
**Type**: String  
**Default**: `'rgba(150,150,150,0.2)'`  
**Scenario**: Adjust shadow color and transparency.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      shadowStyle: {
        color: 'rgba(255,38,89,0.3)' // Semi-transparent pink shadow
      }
    }
  },
  // Other configurations...
})
```  


##### 6.3.2 `borderWidth` Sub-property  
**Function**: Sets shadow border width.  
**Type**: Number  
**Default**: 0  
**Scenario**: Add a border to the shadow.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      shadowStyle: {
        borderWidth: 1 // Shadow border
      }
    }
  },
  // Other configurations...
})
```  


##### 6.3.3 `borderColor` Sub-property  
**Function**: Sets shadow border color.  
**Type**: String  
**Default**: `'rgba(150,150,150,0.2)'`  
**Scenario**: Customize shadow border color.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      shadowStyle: {
        borderColor: '#ff2659f5' // Pink shadow border
      }
    }
  },
  // Other configurations...
})
```  


### 7. `textStyle` Property  
**Function**: Configures text style inside the tooltip.  
**Type**: Object  
**Scenario**: Ensure text contrast and style consistency with the app.  

#### 7.1 `color` Sub-property  
**Function**: Sets text color.  
**Type**: String  
**Default**: `'#fff'`  
**Scenario**: Adjust text color for readability against the background.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    textStyle: {
      color: '#333' // Dark text
    }
  },
  // Other configurations...
})
```  


#### 7.2 `fontWeight` Sub-property  
**Function**: Sets font weight.  
**Type**: String  
**Default**: `'normal'`  
**Options**: `'normal'` / `'bold'` / `'lighter'` / `'bolder'` / numeric values  
**Scenario**: Emphasize important information.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    textStyle: {
      fontWeight: 'bold' // Bold text
    }
  },
  // Other configurations...
})
```  


#### 7.3 `fontFamily` Sub-property  
**Function**: Sets font family.  
**Type**: String  
**Default**: `'sans-serif'`  
**Scenario**: Maintain consistent app typography.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    textStyle: {
      fontFamily: 'Arial' // Specify font
    }
  },
  // Other configurations...
})
```  


#### 7.4 `fontSize` Sub-property  
**Function**: Sets font size.  
**Type**: Number  
**Default**: 14  
**Scenario**: Adjust font size for different chart dimensions.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    textStyle: {
      fontSize: 16 // Larger font
    }
  },
  // Other configurations...
})
```  


### 8. `animationCurve` Property  
**Function**: Sets tooltip show/hide animation easing.  
**Type**: String  
**Default**: `'easeOutCubic'`  
**Options**: CSS-supported curves (e.g., `'linear'`, `'ease'`, `'ease-in'`)  
**Scenario**: Customize animation feel.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    animationCurve: 'ease-in-out' // Smooth in-out animation
  },
  // Other configurations...
})
```  


### 9. `animationFrame` Property  
**Function**: Sets tooltip animation duration (ms).  
**Type**: Number  
**Default**: 0 (no animation)  
**Scenario**: Control animation speed; 0 disables animation.  

```typescript
@State tooltipOption: Options = new Options({
  tooltip: {
    animationFrame: 300 // 300ms animation
  },
  // Other configurations...
})
```  


### Practical Application Example  
Here's a complete tooltip configuration demonstrating a custom-styled tooltip:  

```typescript
import { McHorBarChart, Options } from '@mcui/mccharts'

@Entry
@Component
struct Index {
  @State tooltipOption: Options = new Options({
    title: {
      show: true,
      text: 'Temperature Trend',
      right: 20,
      top: 30
    },
    xAxis: {
      data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
    },
    yAxis: {
      name: 'Temperature (°C)'
    },
    tooltip: {
      show: true,
      padding: 12,
      backgroundColor: 'rgba(255,255,255,0.95)',
      borderWidth: 1,
      borderColor: '#ff2659f5',
      axisPointer: {
        type: 'shadow',
        shadowStyle: {
          color: 'rgba(255,38,89,0.1)',
          borderWidth: 1,
          borderColor: 'rgba(255,38,89,0.2)'
        }
      },
      textStyle: {
        color: '#333',
        fontWeight: 'bold',
        fontFamily: 'Arial',
        fontSize: 14
      },
      animationCurve: 'ease-out',
      animationFrame: 200
    },
    series: [
      { name: 'Max Temp', data: [22, 23, 25, 28, 26, 24, 21] },
      { name: 'Min Temp', data: [12, 13, 14, 16, 15, 13, 11] }
    ]
  })

  build() {
    Row() {
      McHorBarChart({ options: this.tooltipOption })
    }
    .height('50%')
    .width('100%')
  }
}
```  

This example creates a tooltip with a white background, pink border, shadow indicator, bold dark text, and a 200ms fade-out animation—ideal for light-themed apps, balancing visibility and professionalism.  


### Conclusion  
This wraps up our guide to tooltip properties in McHorBarChart! Use these configurations to build visually appealing and functional data visualizations. If you have questions, leave them in the comments. Happy coding! 📊
