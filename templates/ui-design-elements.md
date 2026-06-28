# UI 设计要素模板

> 本模板定义了原型设计中的 UI 设计要素（设计令牌）。所有颜色使用 #RRGGBB 十六进制格式。
> 可以直接使用此模板，也可以在任务目录中放入自定义的 `ui-design-elements.md` 覆盖。

---

## 色板

```json
{
  "colors": {
    "primary": "#007AFF",
    "primary_light": "#4DA3FF",
    "primary_dark": "#0055CC",
    "secondary": "#FF9500",
    "success": "#34C759",
    "warning": "#FFCC00",
    "danger": "#FF3B30",
    "info": "#5AC8FA",
    "background": "#F5F5F5",
    "surface": "#FFFFFF",
    "surface_secondary": "#F0F0F0",
    "border": "#E0E0E0",
    "divider": "#EEEEEE",
    "text_primary": "#333333",
    "text_secondary": "#666666",
    "text_tertiary": "#999999",
    "text_on_primary": "#FFFFFF",
    "text_link": "#007AFF",
    "disabled": "#CCCCCC",
    "overlay": "rgba(0,0,0,0.4)",
    "shadow": "rgba(0,0,0,0.1)"
  }
}
```

## 字体层级

```json
{
  "typography": {
    "heading_large": { "fontFamily": "PingFang SC", "fontSize": 28, "fontWeight": "bold", "lineHeight": 36 },
    "heading_medium": { "fontFamily": "PingFang SC", "fontSize": 22, "fontWeight": "bold", "lineHeight": 30 },
    "heading_small": { "fontFamily": "PingFang SC", "fontSize": 18, "fontWeight": "semibold", "lineHeight": 26 },
    "title": { "fontFamily": "PingFang SC", "fontSize": 17, "fontWeight": "semibold", "lineHeight": 24 },
    "body": { "fontFamily": "PingFang SC", "fontSize": 16, "fontWeight": "regular", "lineHeight": 24 },
    "body_small": { "fontFamily": "PingFang SC", "fontSize": 14, "fontWeight": "regular", "lineHeight": 22 },
    "caption": { "fontFamily": "PingFang SC", "fontSize": 12, "fontWeight": "regular", "lineHeight": 18 },
    "label": { "fontFamily": "PingFang SC", "fontSize": 11, "fontWeight": "regular", "lineHeight": 16 }
  }
}
```

## 间距体系

```json
{
  "spacing": {
    "xs": 4,
    "sm": 8,
    "md": 12,
    "lg": 16,
    "xl": 24,
    "xxl": 32,
    "page_margin": 16,
    "card_gap": 12,
    "element_gap": 8,
    "section_gap": 20
  }
}
```

## 圆角

```json
{
  "border_radius": {
    "none": 0,
    "sm": 4,
    "md": 8,
    "lg": 12,
    "xl": 16,
    "full": "50%",
    "button": 8,
    "card": 12,
    "input": 8,
    "modal": 16,
    "avatar": "50%"
  }
}
```

## 组件尺寸

```json
{
  "dimensions": {
    "navigation_bar_height": 44,
    "tab_bar_height": 49,
    "status_bar_height": 44,
    "button_small": { "height": 32, "padding_h": 12 },
    "button_medium": { "height": 40, "padding_h": 16 },
    "button_large": { "height": 48, "padding_h": 20 },
    "input_height": 40,
    "input_height_large": 48,
    "icon_small": 16,
    "icon_medium": 24,
    "icon_large": 32,
    "avatar_small": 24,
    "avatar_medium": 40,
    "avatar_large": 56,
    "card_min_height": 80,
    "banner_height": 180,
    "thumbnail_size": 80
  }
}
```

## 阴影

```json
{
  "shadows": {
    "none": "none",
    "sm": "0 1px 3px rgba(0,0,0,0.08)",
    "md": "0 2px 8px rgba(0,0,0,0.1)",
    "lg": "0 4px 16px rgba(0,0,0,0.12)",
    "xl": "0 8px 24px rgba(0,0,0,0.15)",
    "card": "0 2px 8px rgba(0,0,0,0.1)",
    "modal": "0 8px 24px rgba(0,0,0,0.2)"
  }
}
```

## 组件样式

```json
{
  "component_styles": {
    "navigation_bar": {
      "backgroundColor": "#FFFFFF",
      "foregroundColor": "#333333",
      "borderBottom": "1px solid #E0E0E0"
    },
    "tab_bar": {
      "backgroundColor": "#FFFFFF",
      "activeColor": "#007AFF",
      "inactiveColor": "#999999",
      "borderTop": "1px solid #E0E0E0"
    },
    "button_primary": {
      "backgroundColor": "#007AFF",
      "textColor": "#FFFFFF",
      "borderRadius": 8,
      "fontSize": 16
    },
    "button_outline": {
      "borderColor": "#007AFF",
      "textColor": "#007AFF",
      "backgroundColor": "transparent",
      "borderRadius": 8,
      "borderWidth": 1
    },
    "card": {
      "backgroundColor": "#FFFFFF",
      "borderRadius": 12,
      "padding": 16,
      "shadow": "0 2px 8px rgba(0,0,0,0.1)"
    },
    "input": {
      "backgroundColor": "#F5F5F5",
      "borderRadius": 8,
      "borderColor": "#E0E0E0",
      "textColor": "#333333",
      "placeholderColor": "#999999",
      "height": 40,
      "paddingH": 12
    },
    "tag": {
      "backgroundColor": "#F0F0F0",
      "textColor": "#666666",
      "borderRadius": 4,
      "paddingH": 8,
      "height": 24,
      "fontSize": 12
    },
    "badge": {
      "backgroundColor": "#FF3B30",
      "textColor": "#FFFFFF",
      "borderRadius": 9,
      "minWidth": 18,
      "height": 18,
      "fontSize": 11
    }
  }
}
```

## 图标规范
* 图标库：统一使用 Material Symbols Rounded。
* 图标尺寸：仅使用 16px、20px、24px 三种，与文字系统对齐。
* 图标颜色：继承父级文字颜色，若需独立指定，使用 --text-secondary 或 --primary。
* 关键约束：生成图标时，必须同时设置 fontSize、width、height 三个属性，且值相等。

## 组件规范

> 使用 `mcp_pencil_set_variables` 注入设计令牌，用`reusable: true`创建`Button/Primary`等组件通过`ref`进行复用，并以 ComponentName/Size/Variant 格式命名。

