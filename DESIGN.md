---
version: alpha
name: Windows Fluent UI for OpenClaw
description: Windows Fluent UI for OpenClaw is the design system for OpenClaw's native Windows companion suite, a WinUI 3 system-tray app that connects your PC to OpenClaw, the AI-powered personal assistant. The app pairs your PC to an OpenClaw gateway, exposes allowlisted Windows node capabilities over MCP, and guides first-run pairing through a setup wizard. Its interface follows Windows Fluent design conventions (Mica surfaces, the user's system accent, and Segoe UI Variable type) so it feels like a quiet, native extension of the OS rather than a bolted-on dashboard.
colors:
  ink: "#1b1b1b"
  paper: "#f3f3f3"
  surface: "#fbfbfb"
  muted: "#5d5d5d"
  line: "#e5e5e5"
  accent: "#0067c0"
  accentInk: "#ffffff"
  positive: "#0f7b0f"
  warning: "#9d5d00"
  critical: "#c42b1c"
  subtleHover: rgba(0,0,0,0.037)
  subtlePressed: rgba(0,0,0,0.024)
  subtleButtonFill: "#ffffff00"
  subtleButtonHoverFill: "#00000009"
  subtleButtonPressedFill: "#00000006"
  subtleButtonText: "#000000e4"
  subtleButtonHoverText: "#000000e4"
  subtleButtonPressedText: "#0000009e"
  subtleButtonDisabledText: "#0000005c"
  subtleButtonBorder: "#ffffff00"
  subtleButtonHoverBorder: "#ffffff00"
  subtleButtonPressedBorder: "#ffffff00"
  control: "#ffffff"
  controlHover: rgba(249,249,249,0.502)
  controlDisabled: rgba(249,249,249,0.302)
  disabledText: rgba(0,0,0,0.361)
  controlLine: "#ececec"
  accentSubtle: "#1a75c7"
  nativeText: "#000000e4"
  personPictureFill: "#00000018"
  personPictureStroke: "#0000000f"
  toggleOffFill: "#00000006"
  toggleOffHoverFill: "#0000000f"
  toggleOffPressedFill: "#00000018"
  toggleOffDisabledFill: "#ffffff00"
  toggleOffStroke: "#00000072"
  toggleOffHotStroke: "#00000072"
  toggleDisabledStroke: "#00000037"
  toggleOnHoverFill: "#0067c0e6"
  toggleOnPressedFill: "#0067c0cc"
  toggleOnDisabledFill: "#00000037"
  toggleOnStroke: "#ffffff00"
  toggleOnHotStroke: "#ffffff00"
  toggleOnDisabledStroke: "#ffffff00"
  toggleOffKnob: "#0000009e"
  toggleOffHotKnob: "#0000009e"
  toggleOnHotKnob: "#ffffff"
  toggleOnDisabledKnob: "#ffffff"
  infoErrorFill: "#fde7e9"
  infoWarningFill: "#fff4ce"
  infoSuccessFill: "#dff6dd"
  infoAttentionFill: "#f6f6f680"
  infoErrorIcon: "#c42b1c"
  infoWarningIcon: "#9d5d00"
  infoSuccessIcon: "#0f7b0f"
  infoAttentionIcon: "#0078d4"
  infoIconForeground: "#ffffff"
  infoBorder: "#0000000f"
  infoCloseHoverFill: "#00000009"
  infoClosePressedFill: "#00000006"
  infoCloseHoverText: "#000000e4"
  infoClosePressedText: "#0000009e"
typography:
  display:
    fontFamily: '"Segoe UI Variable Display", "Segoe UI Variable", "Segoe UI", system-ui, sans-serif'
    fontSize: 68px
    fontWeight: 600
    lineHeight: 92px
  titleLarge:
    fontFamily: '"Segoe UI Variable Display", "Segoe UI Variable", "Segoe UI", system-ui, sans-serif'
    fontSize: 40px
    fontWeight: 600
    lineHeight: 52px
  title:
    fontFamily: '"Segoe UI Variable Display", "Segoe UI Variable", "Segoe UI", system-ui, sans-serif'
    fontSize: 28px
    fontWeight: 600
    lineHeight: 36px
  subtitle:
    fontFamily: '"Segoe UI Variable Display", "Segoe UI Variable", "Segoe UI", system-ui, sans-serif'
    fontSize: 20px
    fontWeight: 600
    lineHeight: 28px
  bodyLargeStrong:
    fontFamily: '"Segoe UI Variable Text", "Segoe UI Variable", "Segoe UI", system-ui, sans-serif'
    fontSize: 18px
    fontWeight: 600
    lineHeight: 24px
  bodyLarge:
    fontFamily: '"Segoe UI Variable Text", "Segoe UI Variable", "Segoe UI", system-ui, sans-serif'
    fontSize: 18px
    fontWeight: 400
    lineHeight: 24px
  bodyStrong:
    fontFamily: '"Segoe UI Variable Text", "Segoe UI Variable", "Segoe UI", system-ui, sans-serif'
    fontSize: 14px
    fontWeight: 600
    lineHeight: 20px
  body:
    fontFamily: '"Segoe UI Variable Text", "Segoe UI Variable", "Segoe UI", system-ui, sans-serif'
    fontSize: 14px
    fontWeight: 400
    lineHeight: 20px
  caption:
    fontFamily: '"Segoe UI Variable Small", "Segoe UI Variable", "Segoe UI", system-ui, sans-serif'
    fontSize: 12px
    fontWeight: 400
    lineHeight: 16px
  small:
    fontFamily: '"Segoe UI Variable Text", "Segoe UI Variable", "Segoe UI", system-ui, sans-serif'
    fontSize: 13px
    fontWeight: 400
    lineHeight: 18px
  personInitials:
    fontFamily: '"Segoe UI Variable", "Segoe UI", system-ui, sans-serif'
    fontSize: 40.32px
    fontWeight: 600
    lineHeight: 1
  personSymbol:
    fontFamily: '"Segoe Fluent Icons", "Segoe MDL2 Assets", sans-serif'
    fontSize: 40.32px
    fontWeight: 600
    lineHeight: 1
  infoSymbol:
    fontFamily: '"Segoe Fluent Icons", "Segoe MDL2 Assets", sans-serif'
    fontSize: 16px
    fontWeight: 400
    lineHeight: 16px
spacing:
  "1": 4px
  "2": 8px
  "3": 12px
  "4": 16px
  "5": 24px
  "6": 32px
  "7": 48px
  "8": 64px
  textControlLeft: 10px
  textControlTop: 5px
  textControlEnd: 6px
  buttonHorizontal: 11px
  buttonTop: 5px
  buttonBottom: 6px
  infoTextTop: 14px
  infoIconGap: 14px
rounded:
  sm: 4px
  md: 8px
  lg: 12px
  bubble: 12px
  composer: 20px
  pill: 999px
x-colophon:
  version: 1
  tokens:
    $schema: https://agents.design/schema/v1
    pages:
      - id: setup
        name: Setup
        description: Onboarding controls and wizard compositions.
        content: Production reference from OpenClaw.SetupEngine.UI. Basic controls remain in Components; these previews compose those shared definitions.
        components:
          - SetupProgressIndicator
          - RecommendedBadge
          - ProviderArtwork
          - SetupOptionCard
          - CapabilityOptionRow
          - SetupPhaseStatus
          - SetupWizardShell
      - id: chat
        name: Chat
        description: Chat controls, identity badges, and the main workspace.
        content: Production reference for Reactor chat and the native Home and Sessions workspace. Includes the workspace connection and notification flyouts. Shared building blocks remain in Components.
        components:
          - ComposerPicker
          - ComposerPickerOptions
          - ChatBubble
          - ChatComposer
          - ChatThread
          - ChatCopyButton
          - AgentIdentityBadge
          - UserIdentityBadge
          - ConnectionStatusFlyout
          - NotificationFlyout
          - WorkspaceShell
          - ExampleScreen
      - id: settings
        name: Settings
        description: Settings controls, rows, expanders, and window composition.
        content: Production reference from OpenClaw.Tray.WinUI settings pages and HubWindow. The trailing control owns interaction on static settings cards. Shared building blocks remain in Components.
        components:
          - SettingsSectionHeader
          - SettingsCard
          - SettingsToggleRow
          - SettingsExpanderRow
          - SettingsWindowShell
    meta:
      version: 1
      updatedBy: xaml+manual
      note: These tokens are the source of truth for DESIGN (brand, color, type, spacing, principles) and are framework-agnostic, and components.jsx shows design intent for the canvas preview, not shipping code. They were captured by manual inspection of the repo's WinUI 3 / XAML and C# surfaces (the CSS/JSX scanner finds no files in a XAML repo) and map to Windows Fluent system resources (SystemAccentColor, Mica, Segoe UI Variable). To ship, port the design into native code via the port targets in `authority`. Edit in the Design System canvas or directly.
    authority:
      designSource: self
      owner: OpenClaw Windows (openclaw/openclaw-windows-node)
      syncProcess: Tokens are captured by manual inspection of the app's WinUI 3 XAML/C# Fluent resources; re-inspect and update this file when the app's ThemeResource mappings or SystemAccentColor usage change.
      tooling:
        name: winapp (WinAppCli)
        source: https://github.com/microsoft/WinAppCli
        role: The Windows App Development CLI is the single build/packaging tool for both port targets below. Both the WinUI 3 (XAML) shell and the Reactor chat surface now build, package, and generate app identity, manifests, and certificates through winapp, so treat it as the port authority's build toolchain.
      port:
        authoritySource: Native WinUI 3 / C# (Windows Fluent)
        syncSource: https://github.com/microsoft/win-dev-skills
        toolingSource: https://github.com/microsoft/WinAppCli
        helperAgent: win-dev-skills
      portOverrides:
        - area: chat
          components:
            - ChatBubble
            - ChatComposer
            - ChatThread
          authoritySource: Reactor (Microsoft.UI.Reactor)
          syncSource: https://github.com/microsoft/microsoft-ui-reactor
          toolingSource: https://github.com/microsoft/WinAppCli
          helperAgent: ""
    shadows:
      - name: sm
        value: 0 1px 2px rgba(0,0,0,0.10)
      - name: md
        value: 0 4px 16px rgba(0,0,0,0.12)
      - name: lg
        value: 0 12px 40px rgba(0,0,0,0.16)
    principles:
      - Defer to Windows. Theme off SystemAccentColor and Fluent resources so the app follows the user's accent, light/dark, and high-contrast choices.
      - One accent, and it means "act here". Selection, focus, and primary actions share the system accent; don't spend it on decoration.
      - Hierarchy over decoration. Size, weight, and space do the work before color does.
      - "State must be legible: connected, pairing, and error states read clearly via positive/warning/critical, never color alone."
      - No hard-coded hex in UI. Use tokens/theme resources so dark and high-contrast modes stay correct.
      - "Motion is a cue, not a garnish: 120-200ms ease-out, no bounce."
    brand:
      tagline: A calm native Windows companion for your AI assistant.
      surface: product
      voice: Clear, respectful, and native to Windows. Explain pairing, permissions, and security plainly. State what will happen and why; never alarmist, never hype.
      personality:
        - native
        - trustworthy
        - calm
        - precise
      antiReferences:
        - custom-skinned controls that fight the OS theme
        - neon gradients and glassmorphism overload
        - ignoring the user's system accent or light/dark preference
        - cramming a web dashboard into a desktop window
        - hard-coded hex that breaks in dark or high-contrast mode
    colors:
      ink:
        resource: TextFillColorPrimaryBrush
        themes:
          dark: "#ffffff"
          highContrast: "#ffffff"
        usage: Primary text, headings. Fluent TextFillColorPrimary on light.
      paper:
        resource: ApplicationPageBackgroundThemeBrush
        themes:
          dark: "#202020"
          highContrast: "#000000"
        usage: App / page background. Mica base / ApplicationPageBackground (light).
      surface:
        resource: CardBackgroundFillColorDefaultBrush
        themes:
          dark: "#2b2b2b"
          highContrast: "#000000"
        usage: Cards, flyouts, inputs. Fluent CardBackgroundFillColorDefault.
      muted:
        resource: TextFillColorSecondaryBrush
        themes:
          dark: "#c8c8c8"
          highContrast: "#ffffff"
        usage: Secondary text, captions. Fluent TextFillColorSecondary/Tertiary.
      line:
        resource: CardStrokeColorDefaultBrush
        themes:
          dark: "#303030"
          highContrast: "#ffffff"
        usage: Borders, dividers. Fluent CardStrokeColorDefault / DividerStroke.
      accent:
        resource: AccentFillColorDefaultBrush
        themes:
          dark: "#4cc2ff"
          highContrast: "#ffff00"
        usage: Primary actions, links, selection, focus. Follows SystemAccentColor (default AccentDark1 on light).
      accentInk:
        resource: TextOnAccentFillColorPrimaryBrush
        themes:
          dark: "#000000"
          highContrast: "#000000"
        usage: Text/glyphs on accent fills.
      positive:
        resource: SystemFillColorSuccessBrush
        themes:
          dark: "#6ccb5f"
          highContrast: "#3ff23f"
        usage: Success / connected states. Fluent SystemFillColorSuccess.
      warning:
        resource: SystemFillColorCautionBrush
        themes:
          dark: "#fcd116"
          highContrast: "#ffb000"
        usage: Warnings / attention. Fluent SystemFillColorCaution.
      critical:
        resource: SystemFillColorCriticalBrush
        themes:
          dark: "#ff99a4"
          highContrast: "#ff5449"
        usage: Errors, disconnected, destructive. Fluent SystemFillColorCritical.
      subtleHover:
        resource: SubtleFillColorSecondaryBrush
        themes:
          dark: rgba(255,255,255,0.0605)
          highContrast: transparent
        usage: "Hover fill for subtle/transparent controls (icon buttons, inline pickers). Fluent SubtleFillColorSecondary (light #09000000)."
      subtlePressed:
        resource: SubtleFillColorTertiaryBrush
        themes:
          dark: rgba(255,255,255,0.0419)
          highContrast: transparent
        usage: "Pressed fill for subtle/transparent controls. Fluent SubtleFillColorTertiary (light #06000000)."
      subtleButtonFill:
        resource: SubtleButtonBackground
        themes:
          dark: "#ffffff00"
          highContrast: "#000000"
        usage: Native SubtleButton rest and disabled fill. SubtleButtonBackgroundDisabled resolves to the same brush in every theme.
      subtleButtonHoverFill:
        resource: SubtleButtonBackgroundPointerOver
        themes:
          dark: "#ffffff0f"
          highContrast: "#000000"
        usage: Native SubtleButton pointer-over fill; high contrast binds SystemColorHighlightTextColorBrush.
      subtleButtonPressedFill:
        resource: SubtleButtonBackgroundPressed
        themes:
          dark: "#ffffff0a"
          highContrast: "#000000"
        usage: Native SubtleButton pressed fill; high contrast binds SystemColorHighlightTextColorBrush.
      subtleButtonText:
        resource: SubtleButtonForeground
        themes:
          dark: "#ffffff"
          highContrast: "#ffffff"
        usage: Native SubtleButton rest foreground; high contrast binds SystemColorButtonTextColorBrush.
      subtleButtonHoverText:
        resource: SubtleButtonForegroundPointerOver
        themes:
          dark: "#ffffff"
          highContrast: "#ffffff"
        usage: Native SubtleButton pointer-over foreground; high contrast binds SystemControlHighlightBaseHighBrush.
      subtleButtonPressedText:
        resource: SubtleButtonForegroundPressed
        themes:
          dark: "#ffffffc5"
          highContrast: "#ffffff"
        usage: Native SubtleButton pressed foreground uses TextFillColorSecondaryBrush, not the normal foreground.
      subtleButtonDisabledText:
        resource: SubtleButtonForegroundDisabled
        themes:
          dark: "#ffffff5d"
          highContrast: "#808080"
        usage: Native SubtleButton disabled foreground uses TextFillColorDisabledBrush, not muted text.
      subtleButtonBorder:
        resource: SubtleButtonBorderBrush
        themes:
          dark: "#ffffff00"
          highContrast: "#ffffff00"
        usage: Transparent 1px native border retained in layout. SubtleButtonBorderBrushDisabled is also transparent in every theme.
      subtleButtonHoverBorder:
        resource: SubtleButtonBorderBrushPointerOver
        themes:
          dark: "#ffffff00"
          highContrast: "#ffff00"
        usage: Preview-only transparent border in light/dark avoids painting the translucent hover fill twice at the edge. Native WinUI uses the matching subtle-fill brush with InnerBorderEdge clipping. High contrast retains SystemColorHighlightColorBrush.
      subtleButtonPressedBorder:
        resource: SubtleButtonBorderBrushPressed
        themes:
          dark: "#ffffff00"
          highContrast: "#000000"
        usage: Preview-only transparent border in light/dark avoids painting the translucent pressed fill twice at the edge. Native WinUI uses the matching subtle-fill brush with InnerBorderEdge clipping. High contrast retains SystemColorHighlightTextColorBrush.
      control:
        resource: ControlFillColorDefaultBrush
        themes:
          dark: "#2d2d2d"
          highContrast: "#000000"
        usage: Fill for input/entry controls (combo boxes, text fields, the chat composer). Fluent ControlFillColorDefault (distinct from the Card surface used for cards/flyouts).
      controlLine:
        resource: ControlStrokeColorDefaultBrush
        themes:
          dark: "#353535"
          highContrast: "#ffffff"
        usage: Border for input/entry controls (combo boxes, text fields, composer, avatars). Fluent ControlStrokeColorDefault (distinct from the Card/divider stroke used for cards).
      controlHover:
        resource: ControlFillColorSecondaryBrush
        themes:
          dark: rgba(255,255,255,0.0824)
          highContrast: "#000000"
        usage: TextBox pointer-over fill. In high contrast the native resource follows SystemColorButtonFaceColor.
      controlDisabled:
        resource: ControlFillColorDisabledBrush
        themes:
          dark: rgba(255,255,255,0.0431)
          highContrast: "#000000"
        usage: Disabled input fill. In high contrast the native resource follows SystemColorButtonFaceColor.
      disabledText:
        resource: TextFillColorDisabledBrush
        themes:
          dark: rgba(255,255,255,0.365)
          highContrast: "#808080"
        usage: Disabled input text. In high contrast the native resource follows SystemColorGrayTextColor.
      accentSubtle:
        resource: AccentFillColorSecondaryBrush
        themes:
          dark: "#47b6ef"
          highContrast: "#ffff00"
        usage: Softer accent fill for the user's own chat bubble. The chat surface binds the chat-local ChatUserBrush (Windows accent at low opacity, for example SystemAccentColorLight2 at 12% on dark and SystemAccentColorDark1 at 8% on light, with the full system highlight in high contrast). AccentFillColorSecondary is the closest standard Fluent approximation for preview.
      nativeText:
        resource: TextFillColorPrimaryBrush
        themes: { dark: "#ffffff", highContrast: "#ffffff" }
        usage: Alpha-preserving native foreground for PersonPicture and InfoBar, including colored backgrounds.
      personPictureFill:
        resource: PersonPictureEllipseFillThemeBrush
        themes: { dark: "#ffffff12", highContrast: "#000000" }
      personPictureStroke:
        resource: PersonPictureEllipseFillStrokeBrush
        themes: { dark: "#00000019", highContrast: "#ffffff" }
      toggleOffFill:
        resource: ToggleSwitchFillOff
        themes: { dark: "#00000019", highContrast: "#000000" }
      toggleOffHoverFill:
        resource: ToggleSwitchFillOffPointerOver
        themes: { dark: "#ffffff0b", highContrast: "#000000" }
      toggleOffPressedFill:
        resource: ToggleSwitchFillOffPressed
        themes: { dark: "#ffffff12", highContrast: "#000000" }
      toggleOffDisabledFill:
        resource: ToggleSwitchFillOffDisabled
        themes: { dark: "#ffffff00", highContrast: "#000000" }
      toggleOffStroke:
        resource: ToggleSwitchStrokeOff
        themes: { dark: "#ffffff8b", highContrast: "#ffffff" }
      toggleOffHotStroke:
        resource: ToggleSwitchStrokeOffPointerOver
        themes: { dark: "#ffffff8b", highContrast: "#ffff00" }
        usage: Pointer-over and pressed strokes share the same resource values.
      toggleDisabledStroke:
        resource: ToggleSwitchStrokeOffDisabled
        themes: { dark: "#ffffff28", highContrast: "#808080" }
      toggleOnHoverFill:
        resource: ToggleSwitchFillOnPointerOver
        themes: { dark: "#4cc2ffe6", highContrast: "#000000" }
      toggleOnPressedFill:
        resource: ToggleSwitchFillOnPressed
        themes: { dark: "#4cc2ffcc", highContrast: "#000000" }
      toggleOnDisabledFill:
        resource: ToggleSwitchFillOnDisabled
        themes: { dark: "#ffffff28", highContrast: "#000000" }
      toggleOnStroke:
        resource: ToggleSwitchStrokeOn
        themes: { dark: "#ffffff00", highContrast: "#ffff00" }
        usage: Transparent preview stroke models ToggleSwitchOnStrokeThickness=0 in light/dark; high contrast retains the native 1px stroke.
      toggleOnHotStroke:
        resource: ToggleSwitchStrokeOnPointerOver
        themes: { dark: "#ffffff00", highContrast: "#ffffff" }
        usage: Pointer-over and pressed preview strokes are transparent only where native stroke thickness is zero.
      toggleOnDisabledStroke:
        resource: ToggleSwitchStrokeOnDisabled
        themes: { dark: "#ffffff00", highContrast: "#808080" }
        usage: Disabled preview stroke is transparent only where native stroke thickness is zero.
      toggleOffKnob:
        resource: ToggleSwitchKnobFillOff
        themes: { dark: "#ffffffc5", highContrast: "#ffffff" }
      toggleOffHotKnob:
        resource: ToggleSwitchKnobFillOffPointerOver
        themes: { dark: "#ffffffc5", highContrast: "#ffff00" }
        usage: Pointer-over and pressed knob fills share the same resource values.
      toggleOnHotKnob:
        resource: ToggleSwitchKnobFillOnPointerOver
        themes: { dark: "#000000", highContrast: "#ffffff" }
        usage: Pointer-over and pressed knob fills share the same resource values.
      toggleOnDisabledKnob:
        resource: ToggleSwitchKnobFillOnDisabled
        themes: { dark: "#ffffff87", highContrast: "#808080" }
      infoErrorFill:
        resource: InfoBarErrorSeverityBackgroundBrush
        themes: { dark: "#442726", highContrast: "#000000" }
      infoWarningFill:
        resource: InfoBarWarningSeverityBackgroundBrush
        themes: { dark: "#433519", highContrast: "#000000" }
      infoSuccessFill:
        resource: InfoBarSuccessSeverityBackgroundBrush
        themes: { dark: "#393d1b", highContrast: "#000000" }
      infoAttentionFill:
        resource: InfoBarInformationalSeverityBackgroundBrush
        themes: { dark: "#ffffff08", highContrast: "#000000" }
      infoErrorIcon:
        resource: InfoBarErrorSeverityIconBackground
        themes: { dark: "#ff99a4", highContrast: "#ffff00" }
      infoWarningIcon:
        resource: InfoBarWarningSeverityIconBackground
        themes: { dark: "#fce100", highContrast: "#ffff00" }
      infoSuccessIcon:
        resource: InfoBarSuccessSeverityIconBackground
        themes: { dark: "#6ccb5f", highContrast: "#ffff00" }
      infoAttentionIcon:
        resource: InfoBarInformationalSeverityIconBackground
        themes: { dark: "#4cc2ff", highContrast: "#ffff00" }
      infoIconForeground:
        resource: InfoBarErrorSeverityIconForeground
        themes: { dark: "#000000e4", highContrast: "#000000" }
        usage: All four severity icon foreground aliases resolve to this same brush in each theme.
      infoBorder:
        resource: InfoBarBorderBrush
        themes: { dark: "#00000019", highContrast: "#ffffff" }
      infoCloseHoverFill:
        resource: AppBarButtonBackgroundPointerOver
        themes: { dark: "#ffffff0f", highContrast: "#ffff00" }
      infoClosePressedFill:
        resource: AppBarButtonBackgroundPressed
        themes: { dark: "#ffffff0a", highContrast: "#ffff00" }
      infoCloseHoverText:
        resource: AppBarButtonForegroundPointerOver
        themes: { dark: "#ffffff", highContrast: "#000000" }
      infoClosePressedText:
        resource: AppBarButtonForegroundPressed
        themes: { dark: "#ffffffc5", highContrast: "#000000" }
    typography:
      display:
        weights:
          - 400
          - 600
        usage: Page and section titles. Segoe UI Variable Display optical size.
      body:
        weights:
          - 400
          - 600
        usage: Body copy, UI labels, buttons. Segoe UI Variable Text optical size.
      mono:
        family: '"Cascadia Mono", "Cascadia Code", Consolas, "SFMono-Regular", monospace'
        weights:
          - 400
        usage: Commands, endpoints, tokens, logs, timestamps. Used heavily across setup and diagnostics surfaces.
      icon:
        family: '"Segoe Fluent Icons", "Segoe MDL2 Assets", sans-serif'
        weights:
          - 400
        usage: Fluent icon glyphs (checkmarks, chevrons, action glyphs). Ships as WinUI FontIcon/SymbolIcon on SymbolThemeFontFamily (Segoe Fluent Icons); e.g. the selection CheckMark is glyph U+E73E. Chat toolbar aliases (FluentIconCatalog) include ChatSubmit U+E74A (send, up glyph), ChatAttach U+E710 (add), ChevronDown U+E70D (picker chevron), and Stop U+E71A (cancel an active turn). Not for body text.
      scale:
        display:
          role: display
          resource: DisplayTextBlockStyle
        titleLarge:
          role: display
          resource: TitleLargeTextBlockStyle
        title:
          role: display
          resource: TitleTextBlockStyle
        subtitle:
          role: display
          resource: SubtitleTextBlockStyle
        bodyLargeStrong:
          role: body
          resource: BodyLargeStrongTextBlockStyle
        bodyLarge:
          role: body
          resource: BodyLargeTextBlockStyle
        bodyStrong:
          role: body
          resource: BodyStrongTextBlockStyle
        body:
          role: body
          resource: BodyTextBlockStyle
        caption:
          role: body
          resource: CaptionTextBlockStyle
        small:
          role: body
          usage: App-specific dense text at 13/18. Not a named WinUI TextBlock style.
        personInitials:
          role: body
          usage: PersonPicture template text, not a TextBlock style. Default 96px diameter times 0.42, SemiBold; ContentControlThemeFontFamily.
        personSymbol:
          role: body
          usage: PersonPicture Contact/People fallback glyph at the same 42% size; SymbolThemeFontFamily.
        infoSymbol:
          role: body
          usage: InfoBarIconFontSize and InfoBarCloseButtonGlyphSize, both 16px; SymbolThemeFontFamily.
    spacing:
      unit: 4
---

## Overview

Windows Fluent UI for OpenClaw is the design system for OpenClaw's native Windows companion suite: a WinUI 3 system-tray app that connects your PC to OpenClaw, the AI-powered personal assistant. The app pairs your PC to an OpenClaw gateway, exposes allowlisted Windows node capabilities over MCP, and guides first-run pairing through a setup wizard. Its interface follows Windows Fluent design conventions (Mica surfaces, the user's system accent, and Segoe UI Variable type) so it feels like a quiet, native extension of the OS rather than a bolted-on dashboard.

<!-- colophon:note -->
Edit and preview this design with the **Colophon** canvas in the GitHub Copilot app.
Install the optional plugin with `copilot plugin install karkarl/colophon`.
Agents without Colophon can read and edit this file directly.
[Colophon documentation](https://github.com/karkarl/colophon).
<!-- colophon:note -->

This file owns the design tokens and rationale. `x-colophon` preserves preview
themes, production resource mappings, and other Colophon-specific metadata.

**The one-line brief.** A calm native Windows companion for your AI assistant. It should feel like a quiet, trustworthy extension of Windows (Fluent surfaces, the user's own accent color), not a web dashboard wearing a desktop window.

Voice: Clear, respectful, and native to Windows. Explain pairing, permissions, and security plainly. State what will happen and why; never alarmist, never hype. No hype words ("supercharge", "seamless", "revolutionary", "effortless").

Personality: native, trustworthy, calm, precise.

## Colors

- **ink** {colors.ink}: Primary text, headings. Fluent TextFillColorPrimary on light.
- **paper** {colors.paper}: App / page background. Mica base / ApplicationPageBackground (light).
- **surface** {colors.surface}: Cards, flyouts, inputs. Fluent CardBackgroundFillColorDefault.
- **muted** {colors.muted}: Secondary text, captions. Fluent TextFillColorSecondary/Tertiary.
- **line** {colors.line}: Borders, dividers. Fluent CardStrokeColorDefault / DividerStroke.
- **accent** {colors.accent}: Primary actions, links, selection, focus. Follows SystemAccentColor (default AccentDark1 on light).
- **accentInk** {colors.accentInk}: Text/glyphs on accent fills.
- **positive** {colors.positive}: Success / connected states. Fluent SystemFillColorSuccess.
- **warning** {colors.warning}: Warnings / attention. Fluent SystemFillColorCaution.
- **critical** {colors.critical}: Errors, disconnected, destructive. Fluent SystemFillColorCritical.
- **subtleHover** {colors.subtleHover}: Hover fill for subtle/transparent controls (icon buttons, inline pickers). Fluent SubtleFillColorSecondary (light #09000000).
- **subtlePressed** {colors.subtlePressed}: Pressed fill for subtle/transparent controls. Fluent SubtleFillColorTertiary (light #06000000).
- **SubtleButton states:** {colors.subtleButtonFill}, {colors.subtleButtonHoverFill}, {colors.subtleButtonPressedFill}, {colors.subtleButtonText}, {colors.subtleButtonHoverText}, {colors.subtleButtonPressedText}, {colors.subtleButtonDisabledText}, {colors.subtleButtonBorder}, {colors.subtleButtonHoverBorder}, and {colors.subtleButtonPressedBorder} bind the control-specific `SubtleButton*` resources. Fill and text alpha bytes come directly from WinUI. Hover/pressed borders are transparent only in the light/dark browser preview, where the background already covers the border area; painting the same translucent color twice would create an incorrect dark outline. Native resource bindings remain unchanged. Separate border and foreground roles preserve the native high-contrast overrides; the displayed high-contrast swatches represent this preview's black/white/yellow scheme, not fixed system colors.
- **control** {colors.control}: Fill for input/entry controls (combo boxes, text fields, the chat composer). Fluent ControlFillColorDefault, distinct from the Card surface used for cards/flyouts.
- **controlHover** {colors.controlHover}: TextBox pointer-over fill, mapped to `ControlFillColorSecondaryBrush`.
- **controlDisabled** {colors.controlDisabled}: Disabled input fill, mapped to `ControlFillColorDisabledBrush`.
- **disabledText** {colors.disabledText}: Disabled input text, mapped to `TextFillColorDisabledBrush`.
- **controlLine** {colors.controlLine}: Border for input/entry controls (combo boxes, text fields, composer, avatars). Fluent ControlStrokeColorDefault, distinct from the Card/divider stroke used for cards.
- **accentSubtle** {colors.accentSubtle}: Softer accent fill for the user's own chat bubble. The chat surface binds the chat-local `ChatUserBrush` (Windows accent at low opacity), quieter than the full accent reserved for primary actions.

Colors are preview swatches only. Bind each color's mapped `resource` key (in `x-colophon.tokens.colors`) rather than the hex, so light, dark, and high-contrast themes stay correct. Never put gray text on a colored background.

## Typography

The reference follows the nine text styles in the WinUI Gallery Typography page. Sizes and line heights are effective pixels (epx), equivalent to XAML device-independent units; Colophon previews them as CSS pixels. Regular is weight 400 and SemiBold is weight 600. Bind the named WinUI `TextBlock` style in native XAML, for example `Style="{StaticResource BodyTextBlockStyle}"`, rather than recreating it with individual setters.

| Style | Token | Segoe UI Variable optical size / weight | Size / line height | WinUI resource |
| --- | --- | --- | --- | --- |
| Caption | {typography.caption} | Small, Regular | 12 / 16 | `CaptionTextBlockStyle` |
| Body | {typography.body} | Text, Regular | 14 / 20 | `BodyTextBlockStyle` |
| Body Strong | {typography.bodyStrong} | Text, SemiBold | 14 / 20 | `BodyStrongTextBlockStyle` |
| Body Large | {typography.bodyLarge} | Text, Regular | 18 / 24 | `BodyLargeTextBlockStyle` |
| Body Large Strong | {typography.bodyLargeStrong} | Text, SemiBold | 18 / 24 | `BodyLargeStrongTextBlockStyle` |
| Subtitle | {typography.subtitle} | Display, SemiBold | 20 / 28 | `SubtitleTextBlockStyle` |
| Title | {typography.title} | Display, SemiBold | 28 / 36 | `TitleTextBlockStyle` |
| Title Large | {typography.titleLarge} | Display, SemiBold | 40 / 52 | `TitleLargeTextBlockStyle` |
| Display | {typography.display} | Display, SemiBold | 68 / 92 | `DisplayTextBlockStyle` |

Resource mappings are also recorded on `x-colophon.tokens.typography.scale` for inspection. `subtitle` replaces the former `heading` token. The former 40px `display` sample is now correctly named `titleLarge`, with a 52px line height; `display` is the 68px style. Keep standard tracking rather than applying custom negative letter spacing.

**App-specific extension:** {typography.small} remains 13/18, Text Regular, for existing dense controls. It is not one of the named WinUI Gallery styles and has no invented resource mapping.

Use Segoe UI Variable for text and Cascadia Mono (`x-colophon.tokens.typography.mono`) for commands, endpoints, tokens, and logs. Fluent icon glyphs use Segoe Fluent Icons (`x-colophon.tokens.typography.icon`); for example, the selection checkmark is glyph U+E73E, and the chat toolbar uses ChatSubmit (U+E74A), ChatAttach (U+E710), ChevronDown (U+E70D), and Stop (U+E71A).

## Layout

Use the named spacing tokens rather than ad-hoc values. Prefer the `5` and `6` steps between groups so content can breathe. One subject per screen: decide what the screen is for, and let that element win.

The `textControlLeft` (10px), `textControlTop` (5px), and `textControlEnd` (6px) tokens preserve WinUI's `TextControlThemePadding` of 10,5,6,6 without rounding it to the general spacing grid.

The `buttonHorizontal` (11px), `buttonTop` (5px), and `buttonBottom` (6px) tokens preserve WinUI's `ButtonPadding` of 11,5,11,6 (left, top, right, bottom). These are content padding inside the separately retained 1px button border, not a fixed square hit target.

## Information hierarchy

1. **One subject per screen.** Decide what the screen is for and let that element win.
2. **Size and weight before color.** Establish the hierarchy in grayscale first; color is the last 10%.
3. **One accent.** `accent` means "act here" (selection, focus, primary action). If everything is accented, nothing is.
4. **Generous vertical rhythm.** Prefer the `5` and `6` spacing steps between groups; let content breathe.

## Elevation & Depth

Use the named shadows in `x-colophon.tokens.shadows` when elevation is needed. Keep shadows soft and shallow; depth should read as Fluent layering, not drop-shadow decoration.

## Shapes

Use the `rounded` tokens for corner radii: `sm` for buttons and inputs, `md` for cards and flyouts, `lg` for grouped panels, `bubble` (12px) for the user chat bubble and code surfaces (assistant prose is bubbleless), `composer` (20px) for the chat writing surface, and `pill` for status badges and toggles.

## Chat surface

The chat transcript and composer ship via Reactor and follow the native chat visual system in [`docs/CHAT_VISUAL_DESIGN.md`](docs/CHAT_VISUAL_DESIGN.md). They align to the reading rhythm of the released web chat without replacing Windows chrome, native input, or gateway contracts.

- **Semantic brushes.** Chat binds the chat-local resources in `Themes/ChatResources.xaml` (Default/Light/HighContrast), not raw palette hex: `ChatCanvasBrush` (transparent; system window in HC), `ChatComposerBrush` and `ChatCardBrush` (`CardBackgroundFillColorDefault`), `ChatStrokeBrush` (`ControlStrokeColorDefault`), `ChatTextBrush` (`TextFillColorPrimary`), `ChatSecondaryTextBrush` (`TextFillColorSecondary`, used for code text), `ChatUserBrush` (accent at low opacity for the user bubble), `ChatUserTextBrush` (`TextFillColorPrimary`), `ChatPickerAccentBrush` (accent variants for picker triggers), and `ChatCopySuccessBrush` (`SystemFillColorSuccess`).
- **Surface layering.** The Hub title bar and expanded navigation pane reveal Mica; `NavigationViewContentBackground` supplies one content layer (`LayerFillColorDefaultBrush`; system window in HC). The chat canvas is transparent so it neither hides nor doubles that layer, and the composer and code cards use the card fill above it. The standalone chat window uses the same Mica plus one content layer.
- **Geometry.** The reading column is capped at 768px with a 16px prose inset; outer gutters are 12px below 640px and 40px above. The avatar is omitted below 960px. The writing surface uses the `composer` (20px) radius, a 16px editor inset, and a 112px minimum height. Assistant turns are bubbleless: their prose flows in the reading column with no card or fill, so the transcript reads like a document. Only the user's own message and code blocks sit on a surface with the `bubble` (12px) radius. All spacing stays on the 4px grid.
- **Footer controls.** One bottom row keeps Attach, session, model, effort, voice, and the primary Send/Stop. The model picker is a native flyout with an AutoSuggestBox over a grouped single-selection list. Effort uses a native discrete slider with a compact gauge trigger (a WinUI-path rendering, not a font glyph) at narrow widths. Copy actions confirm with a `ChatCopySuccessBrush` checkmark and announce Copied.

## Workspace shell

The landing window is the native Home and Sessions workspace (`Windows/WorkspaceWindow.xaml`, shipped in #1541). It is a Mica window with a title bar, a 256px left `NavigationView` pane, and a content host that mounts the Reactor chat. Settings remains an independent native companion window.

- **Pane.** The `NavigationViewExpandedPaneBackground` reveals Mica. The PaneHeader stacks a Back/Forward toolbar of subtle icon buttons over a transparent assistant selector (a borderless `ComboBox` rendering the selected agent through `AgentIdentityBadge`, with a New agent option that carries the `add` glyph U+E710). The menu lists a Home item, then a Sessions header whose inline add button starts a conversation, then one reusable row per session. Selected nav and session rows use the native subtle selection background with a leading `accent` indicator; rows use the `sm` (ControlCornerRadius) corners.
- **Owner footer.** The PaneFooter pairs an Owner button with a Notifications bell. The Owner button is the `UserIdentityBadge`: it reads the authenticated `users.self` profile as a display name over a live connection-status caption, with a small connection status dot to the left of that caption (the same `positive` / `warning` / `critical` / `muted` states as the connection flyout, never color alone). It falls back honestly to Owner / Disconnected when no profile is available and never encodes authorization state. The bell shows an `InfoBadge` count and opens the notifications flyout.
- **Connection status.** `Controls/GatewayStatusContent.xaml` is a 304px flyout of Gateway, Operator, and Node rows split by 1px `line` dividers, closing with an Open Connection link. Each row pairs a 10px status dot with a body-strong label over a caption `muted` detail, and reveals an `accent` action link (Reconnect, Approve) only when that layer needs one. The dot binds the Fluent system fill for its state: `positive` connected, `warning` attention, `critical` error, `muted` unknown, never color alone.
- **Notifications.** `Controls/NotificationFlyoutContent.xaml` is a 352px flyout: a Clear all link, a list of notification cards, and a footer pairing Open notifications with an active-count caption. Each card is a `surface` panel with a 1px `line` border, `md` (8px) corners, and 12px padding, laying out a leading severity glyph, a title/message/metadata stack, and a dismiss button; a recurrence count rides a `warning` badge beside the title. An empty state swaps the list for one centered card.
- **Sidebar glyphs.** Pane and toolbar glyphs are Segoe Fluent Icons or the SVGs under `Assets/SidebarIcons` (Chat, Sessions, Notifications, Connection, and the Settings destinations). Toolbar aliases include Back U+E76B, Forward U+E76C, add U+E710, toggle pane U+E90C, dismiss U+E711, and the Ringer notifications glyph U+EA8F.

## Components

Reuse [component patterns](.agents/design/components.jsonc); these describe design intent, not shipping code.
Optional click-through flows live in `.agents/design/prototypes.jsonc`.

The catalog is organized into four families. Colophon's left navigation includes dedicated Setup, Chat, and Settings pages, defined by `x-colophon.tokens.pages` above. Each page selects existing component definitions without copying them, so shared component references continue to resolve. Basic controls live under Components. The installed Colophon version also shows the full catalog on that built-in page; it does not support filtering Components down to basic controls.

Every interactive control documents its hover and pressed states; static controls say so. States bind Fluent resources (`SubtleFillColorSecondary` for hover, `SubtleFillColorTertiary` for pressed, accent variants for primary actions), never raw hex.

- **Basic controls.** Button (primary/standard/subtle), SubtleButton (native default style), HyperlinkButton, TextBox, Field, Badge, ToggleSwitch, StatusDot, Avatar, InfoBar, and Card. TextBox is the reusable default WinUI single-line input. Field composes a label and TextBox; its Gateway address example passes the label and placeholder into that shared control.
- **Setup.** SetupProgressIndicator, RecommendedBadge, ProviderArtwork, SetupOptionCard, CapabilityOptionRow, SetupPhaseStatus, and the SetupWizardShell frame, ported from `OpenClaw.SetupEngine.UI`.
- **Chat.** ChatBubble, ChatComposer, ChatThread, ComposerPicker, ComposerPickerOptions, and ChatCopyButton, plus the native workspace identity controls (AgentIdentityBadge, UserIdentityBadge), ConnectionStatusFlyout, NotificationFlyout, WorkspaceShell, and ExampleScreen. See the Chat surface and Workspace shell sections.
- **Settings.** SettingsSectionHeader, SettingsCard, SettingsToggleRow, SettingsExpanderRow, and the SettingsWindowShell host frame, ported from `OpenClaw.Tray.WinUI` pages and `HubWindow`.

TextBox ships as the stock `Microsoft.UI.Xaml.Controls.TextBox`, as used by `DirectUrlBox` in `Pages/ConnectionPage.xaml`, not a custom control template. The Colophon preview uses 14px body text, 32px single-line height, `sm` corners, exact text-control padding, pointer-over and disabled resource tokens, and the accent focus underline. WinUI has no separate pressed background for the input itself; pressing enters its focused state. The browser preview approximates the native elevation border with `controlLine` and does not reproduce the native focused-fill transition or clear-button template.

Card binds its title to `subtitle` (`SubtitleTextBlockStyle`, 20/28 SemiBold) and its description to `body` (`BodyTextBlockStyle`, 14/20 Regular). Its Open report action references the shared HyperlinkButton, not a separately styled link. The card remains static while the action inherits the shared control's typography, hover, pressed, disabled, and focus states.

StatusDot is a non-interactive 10x10 indicator with `pill` corners and a semantic fill. Its standalone preview uses explicit Auto Layout so the empty span retains its width and height instead of collapsing as inline text.

SubtleButton follows [`SubtleButtonStyle` and `ButtonPadding` in WinUI](https://github.com/microsoft/microsoft-ui-xaml/blob/main/controls/dev/CommonStyles/Button_themeresources.xaml): 11,5,11,6 content padding, a 1px border, `ControlCornerRadius` (4px), and normal-weight 14px content. The default example is content-sized text, not a 40x40 icon button. The workspace's 40x40 icon buttons and their local padding overrides are usage variants, not defaults of the style. Rest and disabled backgrounds remain transparent in light/dark; hover and pressed states change background, border, and foreground through the native resource aliases above. Ship with `Style="{StaticResource SubtleButtonStyle}"` and leave its template intact.

The browser paints backgrounds through the border box rather than using WinUI's `BackgroundSizing=InnerBorderEdge`. SubtleButton therefore keeps its 1px border transparent in light/dark, including hover and pressed states, so the edge receives exactly one layer of the subtle fill. High-contrast borders and keyboard-only focus remain visible. This preview compensation must not replace the native `SubtleButtonStyle` resource bindings.

Colophon's browser preview retains limitations: its body line box is 20px rather than native text measurement, and its shared focus outline and 160ms state transition do not reproduce the native system focus visual (`FocusVisualMargin=-3`) and 83ms background brush transition. Exact native rendering remains owned by WinUI, not this browser approximation.

### Native ToggleSwitch, PersonPicture, and InfoBar references

`ToggleSwitch` remains a **static track reference**, not a working switch, pending interactive renderer support. Keep one shared component rather than a gallery of static interaction states. The [native template](https://github.com/microsoft/microsoft-ui-xaml/blob/main/controls/dev/CommonStyles/ToggleSwitch_themeresources.xaml) uses a 40x20 track, a 12x12 resting/disabled knob, a 14x14 pointer-over knob, and a 17x14 pressed knob. The full native control also owns its header, On/Off content, 12px track-to-content gap, 10px pre/post margins, and 154px minimum width; these are not part of the isolated track.

On/Off movement is native `RepositionThemeAnimation` with a 20px endpoint displacement and template-calculated `KnobOnToOffOffset` / `KnobOffToOnOffset`. Pointer-over/pressed knob resizing uses `ControlFasterAnimationDuration` (83ms) and `ControlFastOutSlowInKeySpline` (0,0,0,1); disabled resizing uses `ControlNormalAnimationDuration` (250ms). Preserve WinUI's Dragging transitions and system animation settings rather than replacing them with the general motion guideline. The installed Colophon renderer cannot persist checked state, animate geometry, or express these transitions. The remaining reference does not prove animation, dragging, keyboard switching, or the on-knob `CircleElevationBorderBrush`.

`Avatar` follows [DefaultPersonPictureStyle](https://github.com/microsoft/microsoft-ui-xaml/blob/main/controls/dev/PersonPicture/PersonPicture.xaml): 96x96 by default, a 1px ellipse stroke, `PersonPictureEllipseFillThemeBrush`, and semibold initials sized to `max(1, diameter * 0.42)`. At the default size this is 40.32px, not a 13px body label. `AvatarStates` also shows the native Contact (U+E77B) and People (U+E716) fallbacks. PersonPicture is non-interactive and has no hover/pressed states; an enclosing button owns those. Production 32px and 24px usages are size overrides, not the default. Native photo clipping, initials generation, badge layout, and `TextLineBounds=Tight` remain native behavior, not browser parity claims.

`InfoBar` follows the [native template](https://github.com/microsoft/microsoft-ui-xaml/blob/main/controls/dev/InfoBar/InfoBar.xaml) and [resources](https://github.com/microsoft/microsoft-ui-xaml/blob/main/controls/dev/InfoBar/InfoBar_themeresources.xaml). `InfoBarStates` shows all four severities. Both the background and layered 16px icon change with severity. Titles are Body Strong and messages Body, both primary foreground, with 4px corners. The horizontal reference preserves 16px leading padding, 14px icon-to-text spacing, 14px text top offset, 12px title/message spacing, and 16px panel end margin. The 48px content grid plus two 1px borders produces a 50px outer height for a single-line banner.

The close control is `InfoBarCloseButtonStyle` (based on `DefaultButtonStyle` with AppBarButton resource overrides), not SubtleButtonStyle: 38x38 with a 5px margin and a 16px Cancel glyph. Its preview has hover, pressed, disabled, and keyboard-focus visuals, but **does not dismiss the banner**. The installed renderer only supports opening an overlay on click. Native `IsOpen`, `IsClosable`, actions, `InfoBarPanel` responsive reflow, high-contrast 2px border thickness, and native glyph/text rasterization are not reproduced. The preview retains a 1px border in every theme and uses representative high-contrast system colors. These limits prevent a 1:1 native rendering claim; ship the stock controls and their resources, never these SVG/browser stand-ins.

## Do's and Don'ts

Do:

- Defer to Windows: theme off `SystemAccentColor` and Fluent resources so the app follows the user's accent, light/dark, and high-contrast settings.
- Spend the accent sparingly. Selection, focus, and primary actions share the system accent; do not spend it on decoration.
- Let size, weight, and space carry hierarchy before color does.
- Make connection state legible: connected, pairing, and error read via `positive`/`warning`/`critical`, never by color alone.
- Keep motion to 120-200ms ease-out. Animate to explain, not to impress.

Don't:

- Don't hard-code hex in UI; it breaks in dark and high-contrast modes. Use tokens/theme resources.
- Don't put gray text on a colored background.
- Don't nest cards inside cards, or wrap every block in a card.
- Don't reach for bounce/elastic easing; it reads as dated.
- Don't fight the OS theme with custom-skinned controls or glassmorphism overload.

Anti-references: if a mock could be mistaken for a neon-gradient SaaS landing page, or ignores the user's system accent and light/dark preference, start over. Avoid: custom-skinned controls that fight the OS theme; neon gradients and glassmorphism overload; ignoring the user's system accent or light/dark preference; cramming a web dashboard into a desktop window; hard-coded hex that breaks in dark or high-contrast mode.

## Production implementation

The design files are the source of truth for design, and are framework-agnostic. `components.jsonc` shows design intent for preview, not shipping code. Follow `x-colophon.tokens.authority` for port targets, ownership, and synchronization:

- **Default:** surfaces ship as **native WinUI 3 / C#** (Windows Fluent). Port the design into XAML/C# via [win-dev-skills](https://github.com/microsoft/win-dev-skills).
- **Chat surface** (`ChatBubble`, `ChatComposer`, `ChatThread`): ships via **[Reactor](https://github.com/microsoft/microsoft-ui-reactor)**, the React-style framework for this app's chat. Reactor has no dedicated porting agent yet.
- Both port targets build and package through **[winapp (WinAppCli)](https://github.com/microsoft/WinAppCli)**, the Windows App Development CLI, which also generates app identity, manifests, and certificates.

Colors are preview swatches: bind their mapped `resource` keys rather than hard-coding hex values. Preserve the light, dark, and high-contrast mappings. The shipping implementation is canonical; component patterns are not shipping code. When you need a value the design doesn't cover, add it here first, then port it into the native/Reactor implementation via the matching reference above.
