大家好，欢迎回来鸿蒙5莓创图表组件的专场，我们这一期来讲解横向柱状图(McHorBarChart)中tooltip属性的详细用法。tooltip是图表中非常重要的交互组件，它能够在用户悬停或点击时显示详细的数据信息。下面我们将全面解析tooltip的各个属性及其子属性。

## 1. show属性

作用：控制提示层是否显示 类型：Boolean 默认值：true 可选值：true(显示)、false(隐藏) 使用场景：当需要完全禁用提示层时，可以设置为false。例如在移动端小尺寸图表中，可能不需要显示tooltip。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    show: false // 完全禁用提示层
  },
  // 其他配置...
})
```

## 2. padding属性

作用：设置提示框内部边距 类型：Number 默认值：10 使用场景：当提示框内容较多时，可以适当增加内边距使显示更美观；在紧凑布局中可以减小内边距。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    padding: 15 // 增大内边距
  },
  // 其他配置...
})
```

## 3. backgroundColor属性

作用：设置提示框背景颜色 类型：String 默认值：'rgba(0,0,0,0.7)' 使用场景：根据应用主题调整提示框背景色，确保与图表整体风格一致且文字可读。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    backgroundColor: 'rgba(255,255,255,0.9)' // 白色半透明背景
  },
  // 其他配置...
})
```

## 4. borderWidth属性

作用：设置提示框边框宽度 类型：Number 默认值：0 使用场景：当需要突出提示框边界时，可以设置边框宽度。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    borderWidth: 1 // 1像素边框
  },
  // 其他配置...
})
```

## 5. borderColor属性

作用：设置提示框边框颜色 类型：String 默认值：'rgba(0,0,0,0.7)' 使用场景：配合borderWidth使用，设置边框颜色。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    borderWidth: 1,
    borderColor: '#ff2659f5' // 设置粉色边框
  },
  // 其他配置...
})
```

## 6. axisPointer属性

作用：配置指示线样式，包括线和阴影两种类型 类型：Object 默认值：见下方子属性 使用场景：用于突出显示当前数据项对应的坐标位置。

### 6.1 type子属性

作用：指示器类型 类型：String 默认值：'line' 可选值：'line'(线型)、'shadow'(阴影型) 使用场景：线型适合精确指示，阴影型适合强调数据范围。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      type: 'shadow' // 使用阴影指示器
    }
  },
  // 其他配置...
})
```

### 6.2 lineStyle子属性

作用：线型指示器的样式配置 类型：Object 默认值：见下方子属性

#### 6.2.1 width子属性

作用：线宽 类型：Number 默认值：1 使用场景：调整指示线粗细。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      lineStyle: {
        width: 2 // 加粗指示线
      }
    }
  },
  // 其他配置...
})
```

#### 6.2.2 type子属性

作用：线的类型 类型：String 默认值：'solid' 可选值：'solid'(实线)、'dashed'(虚线)、'dotted'(点线) 使用场景：虚线或点线可以创建更柔和的视觉指示。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      lineStyle: {
        type: 'dashed' // 虚线指示线
      }
    }
  },
  // 其他配置...
})
```

#### 6.2.3 color子属性

作用：线颜色 类型：String 默认值：'#DDE2EB' 使用场景：调整指示线颜色以匹配图表主题。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      lineStyle: {
        color: '#ff2659f5' // 粉色指示线
      }
    }
  },
  // 其他配置...
})
```

### 6.3 shadowStyle子属性

作用：阴影指示器的样式配置 类型：Object 默认值：见下方子属性

#### 6.3.1 color子属性

作用：阴影颜色 类型：String 默认值：'rgba(150,150,150,0.2)' 使用场景：调整阴影颜色和透明度。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      shadowStyle: {
        color: 'rgba(255,38,89,0.3)' // 粉色半透明阴影
      }
    }
  },
  // 其他配置...
})
```

#### 6.3.2 borderWidth子属性

作用：阴影边框宽度 类型：Number 默认值：0 使用场景：为阴影添加边框。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      shadowStyle: {
        borderWidth: 1 // 添加阴影边框
      }
    }
  },
  // 其他配置...
})
```

#### 6.3.3 borderColor子属性

作用：阴影边框颜色 类型：String 默认值：'rgba(150,150,150,0.2)' 使用场景：设置阴影边框颜色。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    axisPointer: {
      shadowStyle: {
        borderColor: '#ff2659f5' // 粉色阴影边框
      }
    }
  },
  // 其他配置...
})
```

## 7. textStyle属性

作用：配置提示框内文本样式 类型：Object 默认值：见下方子属性 使用场景：确保提示文本与背景有足够对比度，且风格与整体应用一致。

### 7.1 color子属性

作用：文本颜色 类型：String 默认值：'#fff' 使用场景：根据背景色调整文本颜色确保可读性。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    textStyle: {
      color: '#333' // 深色文字
    }
  },
  // 其他配置...
})
```

### 7.2 fontWeight子属性

作用：字体粗细 类型：String 默认值：'normal' 可选值：'normal'、'bold'、'lighter'、'bolder'或数字值 使用场景：强调重要信息。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    textStyle: {
      fontWeight: 'bold' // 加粗文字
    }
  },
  // 其他配置...
})
```

### 7.3 fontFamily子属性

作用：字体类型 类型：String 默认值：'sans-serif' 使用场景：统一应用字体风格。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    textStyle: {
      fontFamily: 'Arial' // 指定字体
    }
  },
  // 其他配置...
})
```

### 7.4 fontSize子属性

作用：字体大小 类型：Number 默认值：14 使用场景：根据图表大小调整字体尺寸。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    textStyle: {
      fontSize: 16 // 增大字体
    }
  },
  // 其他配置...
})
```

## 8. animationCurve属性

作用：提示框显示/隐藏的动画曲线 类型：String 默认值：'easeOutCubic' 可选值：CSS支持的动画曲线，如'linear'、'ease'、'ease-in'等 使用场景：自定义提示框动画效果。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    animationCurve: 'ease-in-out' // 平滑的进出动画
  },
  // 其他配置...
})
```

## 9. animationFrame属性

作用：提示框动画持续时间(毫秒) 类型：Number 默认值：0(无动画) 使用场景：控制动画速度，0表示禁用动画。

```
@State tooltipOption: Options = new Options({
  tooltip: {
    animationFrame: 300 // 300毫秒动画
  },
  // 其他配置...
})
```

## 实际应用案例

下面是一个完整的tooltip配置示例，展示了如何创建一个自定义风格的提示框：

```
import { McHorBarChart, Options } from '@mcui/mccharts'

@Entry
@Component
struct Index {
  @State tooltipOption: Options = new Options({
    title: {
      show: true,
      text: '温度变化趋势',
      right: 20,
      top: 30
    },
    xAxis: {
      data: ['周一', '周二', '周三', '周四', '周五', '周六', '周日']
    },
    yAxis: {
      name: '温度(℃)'
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
    series: [{
      name: '最高气温',
      data: [22, 23, 25, 28, 26, 24, 21]
    }, {
      name: '最低气温',
      data: [12, 13, 14, 16, 15, 13, 11]
    }]
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

在这个案例中，我们创建了一个白色背景、粉色边框的提示框，带有阴影指示器，文字使用深色加粗显示，并有200毫秒的淡出动画。这种配置在浅色背景的应用中非常醒目且专业。

好，这期讲到这里就结束了，希望大家通过这篇文章能够全面掌握McHorBarChart组件中tooltip属性的各种配置方法，在实际开发中灵活运用，创建出既美观又实用的数据可视化效果。如果有任何问题，欢迎在评论区留言讨论！