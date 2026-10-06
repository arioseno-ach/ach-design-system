---
id: .04-datepicker-calendar
name: .04DatepickerCalendar
category: primitive
figma_component_name: ".04 Datepicker Calendar"
figma_url: "https://www.figma.com/design//?node-id=1586-40038"
status: draft
tokens_used:
  - datepicker.calendar.background
  - datepicker.calendar.border
  - borderRadius.sm
  - padding.3
  - padding.2
  - datepicker.header.icon
  - datepicker.header.text
  - padding.1
  - datepicker.weekday.text
  - datepicker.day.text
  - datepicker.day.bg_selected
  - datepicker.day.text_selected
  - datepicker.day.bg_today
  - datepicker.day.text_today
---

# .04DatepickerCalendar

## Code contract

```typescript
interface .04DatepickerCalendarProps {
  children?: React.ReactNode;
  className?: string;
}
```

## Anatomy

```
1. [Root] .04 Datepicker Calendar (COMPONENT)
  2. [Container] Header (FRAME)
    3. [Icon] Icon Left (INSTANCE)
      4. [Element] Vector (VECTOR)
    5. [Label] Month Year (TEXT)
    6. [Icon] Icon Right (INSTANCE)
      7. [Element] Vector (VECTOR)
  8. [Container] Weekdays (FRAME)
    9. [Container] S (FRAME)
      10. [Label] S (TEXT)
    11. [Container] M (FRAME)
      12. [Label] M (TEXT)
    13. [Container] T (FRAME)
      14. [Label] T (TEXT)
    15. [Container] W (FRAME)
      16. [Label] W (TEXT)
    17. [Container] T (FRAME)
      18. [Label] T (TEXT)
    19. [Container] F (FRAME)
      20. [Label] F (TEXT)
    21. [Container] S (FRAME)
      22. [Label] S (TEXT)
  23. [Container] Week 1 (FRAME)
    24. [Container] Empty (FRAME)
    25. [Container] Empty (FRAME)
    26. [Container] Empty (FRAME)
    27. [Container] Empty (FRAME)
    28. [Container] Empty (FRAME)
    29. [Container] 1 (FRAME)
      30. [Label] 1 (TEXT)
    31. [Container] 2 (FRAME)
      32. [Label] 2 (TEXT)
  33. [Container] Week 2 (FRAME)
    34. [Container] 3 (FRAME)
      35. [Label] 3 (TEXT)
    36. [Container] 4 (FRAME)
      37. [Label] 4 (TEXT)
    38. [Container] 5 (FRAME)
      39. [Label] 5 (TEXT)
    40. [Container] 6 (FRAME)
      41. [Label] 6 (TEXT)
    42. [Container] 7 (FRAME)
      43. [Label] 7 (TEXT)
    44. [Container] 8 (FRAME)
      45. [Label] 8 (TEXT)
    46. [Container] 9 (FRAME)
      47. [Label] 9 (TEXT)
  48. [Container] Week 3 (FRAME)
    49. [Container] 10 (FRAME)
      50. [Label] 10 (TEXT)
    51. [Container] 11 (FRAME)
      52. [Label] 11 (TEXT)
    53. [Container] 12 (FRAME)
      54. [Label] 12 (TEXT)
    55. [Container] 13 (FRAME)
      56. [Label] 13 (TEXT)
    57. [Container] 14 (FRAME)
      58. [Label] 14 (TEXT)
    59. [Container] 15 (FRAME)
      60. [Label] 15 (TEXT)
    61. [Container] 16 (FRAME)
      62. [Label] 16 (TEXT)
  63. [Container] Week 4 (FRAME)
    64. [Container] 17 (FRAME)
      65. [Label] 17 (TEXT)
    66. [Container] 18 (FRAME)
      67. [Label] 18 (TEXT)
    68. [Container] 19 (FRAME)
      69. [Label] 19 (TEXT)
    70. [Container] 20 (FRAME)
      71. [Label] 20 (TEXT)
    72. [Container] 21 (FRAME)
      73. [Label] 21 (TEXT)
    74. [Container] 22 (FRAME)
      75. [Label] 22 (TEXT)
    76. [Container] 23 (FRAME)
      77. [Label] 23 (TEXT)
  78. [Container] Week 5 (FRAME)
    79. [Container] 24 (FRAME)
      80. [Label] 24 (TEXT)
    81. [Container] 25 (FRAME)
      82. [Label] 25 (TEXT)
    83. [Container] 26 (FRAME)
      84. [Label] 26 (TEXT)
    85. [Container] 27 (FRAME)
      86. [Label] 27 (TEXT)
    87. [Container] 28 (FRAME)
      88. [Label] 28 (TEXT)
    89. [Container] 29 (FRAME)
      90. [Label] 29 (TEXT)
    91. [Container] 30 (FRAME)
      92. [Label] 30 (TEXT)
  93. [Container] Week 6 (FRAME)
    94. [Container] 31 (FRAME)
      95. [Label] 31 (TEXT)
    96. [Container] Empty (FRAME)
    97. [Container] Empty (FRAME)
    98. [Container] Empty (FRAME)
    99. [Container] Empty (FRAME)
    100. [Container] Empty (FRAME)
    101. [Container] Empty (FRAME)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| .04 Datepicker Calendar | fill | `#FFFFFF` | `datepicker.calendar.background` | `var(--ach-datepicker-calendar-background)` |
| .04 Datepicker Calendar | stroke | `#DCDCDC` | `datepicker.calendar.border` | `var(--ach-datepicker-calendar-border)` |
| .04 Datepicker Calendar | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| .04 Datepicker Calendar | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| .04 Datepicker Calendar | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| .04 Datepicker Calendar | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| .04 Datepicker Calendar | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| .04 Datepicker Calendar | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Vector | fill | `#262626` | `datepicker.header.icon` | `var(--ach-datepicker-header-icon)` |
| Month Year | fill | `#262626` | `datepicker.header.text` | `var(--ach-datepicker-header-text)` |
| Month Year | fontSize | `14px` | `—` | `—` |
| Vector | fill | `#262626` | `datepicker.header.icon` | `var(--ach-datepicker-header-icon)` |
| Weekdays | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| S | fill | `#737373` | `datepicker.weekday.text` | `var(--ach-datepicker-weekday-text)` |
| S | fontSize | `10px` | `—` | `—` |
| M | fill | `#737373` | `datepicker.weekday.text` | `var(--ach-datepicker-weekday-text)` |
| M | fontSize | `10px` | `—` | `—` |
| T | fill | `#737373` | `datepicker.weekday.text` | `var(--ach-datepicker-weekday-text)` |
| T | fontSize | `10px` | `—` | `—` |
| W | fill | `#737373` | `datepicker.weekday.text` | `var(--ach-datepicker-weekday-text)` |
| W | fontSize | `10px` | `—` | `—` |
| T | fill | `#737373` | `datepicker.weekday.text` | `var(--ach-datepicker-weekday-text)` |
| T | fontSize | `10px` | `—` | `—` |
| F | fill | `#737373` | `datepicker.weekday.text` | `var(--ach-datepicker-weekday-text)` |
| F | fontSize | `10px` | `—` | `—` |
| S | fill | `#737373` | `datepicker.weekday.text` | `var(--ach-datepicker-weekday-text)` |
| S | fontSize | `10px` | `—` | `—` |
| Week 1 | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Empty | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Empty | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Empty | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Empty | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Empty | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 1 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 1 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 1 | fontSize | `12px` | `—` | `—` |
| 2 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 2 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 2 | fontSize | `12px` | `—` | `—` |
| Week 2 | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 3 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 3 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 3 | fontSize | `12px` | `—` | `—` |
| 4 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 4 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 4 | fontSize | `12px` | `—` | `—` |
| 5 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 5 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 5 | fontSize | `12px` | `—` | `—` |
| 6 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 6 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 6 | fontSize | `12px` | `—` | `—` |
| 7 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 7 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 7 | fontSize | `12px` | `—` | `—` |
| 8 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 8 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 8 | fontSize | `12px` | `—` | `—` |
| 9 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 9 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 9 | fontSize | `12px` | `—` | `—` |
| Week 3 | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 10 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 10 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 10 | fontSize | `12px` | `—` | `—` |
| 11 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 11 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 11 | fontSize | `12px` | `—` | `—` |
| 12 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 12 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 12 | fontSize | `12px` | `—` | `—` |
| 13 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 13 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 13 | fontSize | `12px` | `—` | `—` |
| 14 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 14 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 14 | fontSize | `12px` | `—` | `—` |
| 15 | fill | `#005CFF` | `datepicker.day.bg_selected` | `var(--ach-datepicker-day-bg_selected)` |
| 15 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 15 | fill | `#FFFFFF` | `datepicker.day.text_selected` | `var(--ach-datepicker-day-text_selected)` |
| 15 | fontSize | `12px` | `—` | `—` |
| 16 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 16 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 16 | fontSize | `12px` | `—` | `—` |
| Week 4 | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 17 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 17 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 17 | fontSize | `12px` | `—` | `—` |
| 18 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 18 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 18 | fontSize | `12px` | `—` | `—` |
| 19 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 19 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 19 | fontSize | `12px` | `—` | `—` |
| 20 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 20 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 20 | fontSize | `12px` | `—` | `—` |
| 21 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 21 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 21 | fontSize | `12px` | `—` | `—` |
| 22 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 22 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 22 | fontSize | `12px` | `—` | `—` |
| 23 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 23 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 23 | fontSize | `12px` | `—` | `—` |
| Week 5 | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 24 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 24 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 24 | fontSize | `12px` | `—` | `—` |
| 25 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 25 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 25 | fontSize | `12px` | `—` | `—` |
| 26 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 26 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 26 | fontSize | `12px` | `—` | `—` |
| 27 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 27 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 27 | fontSize | `12px` | `—` | `—` |
| 28 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 28 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 28 | fontSize | `12px` | `—` | `—` |
| 29 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 29 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 29 | fontSize | `12px` | `—` | `—` |
| 30 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 30 | fill | `#262626` | `datepicker.day.text` | `var(--ach-datepicker-day-text)` |
| 30 | fontSize | `12px` | `—` | `—` |
| Week 6 | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 31 | fill | `#F2F7FF` | `datepicker.day.bg_today` | `var(--ach-datepicker-day-bg_today)` |
| 31 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 31 | fill | `#003EB8` | `datepicker.day.text_today` | `var(--ach-datepicker-day-text_today)` |
| 31 | fontSize | `12px` | `—` | `—` |
| Empty | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Empty | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Empty | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Empty | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Empty | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Empty | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ❌ | Not found — add variant or document manually |
| Pressed | ❌ | Not found — add variant or document manually |
| Focus | ❌ | Not found — add variant or document manually |
| Disabled | ❌ | Not found — add variant or document manually |
| Loading | ❌ | Not found — add variant or document manually |

## Do's and Don'ts

### Do's
- Always use design tokens — never hardcode hex values, pixel sizes, or font names.
- Provide helper text when a control is disabled to explain why.
- Use a single primary action per view or card.
- Follow the token mapping table for all style properties.
- Respect the anatomy structure — maintain the layer hierarchy.

### Don'ts
- Don't override token values with hardcoded `#hex` or inline styles.
- Don't skip disabled, loading, or error states.
- Don't nest this component inside itself.
- Don't remove required accessibility attributes (`role`, `aria-label`, etc.).
- Don't ignore the variant contract — always pass valid variant values.
