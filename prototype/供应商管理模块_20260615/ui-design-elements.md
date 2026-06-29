# UI 设计要素 — 供应商管理模块

## 色板

```json
{
  "colors": {
    "primary": "#0EA5A0",
    "primary_light": "#3ECFC8",
    "primary_dark": "#0A7A76",
    "secondary": "#FF9500",
    "success": "#34C759",
    "warning": "#FFCC00",
    "danger": "#FF3B30",
    "info": "#5AC8FA",
    "background": "#F5F7FA",
    "surface": "#FFFFFF",
    "surface_secondary": "#F0F2F5",
    "border": "#E0E0E0",
    "divider": "#EEEEEE",
    "text_primary": "#333333",
    "text_secondary": "#666666",
    "text_tertiary": "#999999",
    "text_on_primary": "#FFFFFF",
    "text_link": "#0EA5A0",
    "disabled": "#CCCCCC",
    "overlay": "rgba(0,0,0,0.4)",
    "shadow": "rgba(0,0,0,0.1)",
    "gold_tag": "#E6A23C",
    "silver_tag": "#909399",
    "bronze_tag": "#CD7F32",
    "enable_tag": "#67C23A",
    "disable_tag": "#F56C6C"
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

## 组件样式

```json
{
  "component_styles": {
    "navigation_bar": {
      "backgroundColor": "#FFFFFF",
      "foregroundColor": "#333333",
      "borderBottom": "1px solid #E0E0E0"
    },
    "button_primary": {
      "backgroundColor": "#0EA5A0",
      "textColor": "#FFFFFF",
      "borderRadius": 8,
      "fontSize": 14
    },
    "button_outline": {
      "borderColor": "#0EA5A0",
      "textColor": "#0EA5A0",
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
      "backgroundColor": "#F5F7FA",
      "borderRadius": 8,
      "borderColor": "#E0E0E0",
      "textColor": "#333333",
      "placeholderColor": "#999999",
      "height": 40,
      "paddingH": 12
    },
    "tag": {
      "backgroundColor": "#F0F2F5",
      "textColor": "#666666",
      "borderRadius": 4,
      "paddingH": 8,
      "height": 24,
      "fontSize": 12
    },
    "table_header": {
      "backgroundColor": "#F5F7FA",
      "textColor": "#333333",
      "fontWeight": "semibold"
    },
    "table_row_hover": {
      "backgroundColor": "#F0F2F5"
    }
  }
}
```
