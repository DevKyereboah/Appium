# AI Agent Instructions for Appium Mobile Testing Project

## Project Overview

This is a mobile testing automation project using WebDriverIO with Appium for Android app testing, specifically targeting the Google Calendar app. The project follows the Page Object Model (POM) pattern for test organization.

## Key Architecture Patterns

### Page Object Pattern

- Page objects are located in `test/pageobjects/`
- Each page extends the base `Page` class
- Page objects encapsulate selectors and interaction methods
- Example: See `login.page.ts` for pattern implementation

### Test Structure

- Test specs are located in `test/specs/**/*.ts`
- Tests use TypeScript for type safety
- Tests follow WebDriverIO's async/await pattern

## Development Workflow

### Setup & Running Tests

```bash
# Install dependencies
npm install

# Run all tests
npm run wdio
```

### Key Configuration

- WebDriverIO config in `wdio.conf.ts`
- Android device configuration:
  - Platform: Android
  - Version: 16.0
  - App Package: com.google.android.calendar
  - Automation: UiAutomator2

## Project Conventions

### Selector Patterns

- Use getter methods for element selectors
- Prefer ID selectors (`$('#elementId')`) when available
- Example from `login.page.ts`:
  ```typescript
  public get inputUsername() {
      return $('#username');
  }
  ```

### Page Object Methods

- Methods should be descriptive and action-focused
- Use async/await for all WebDriverIO commands
- Encapsulate complex interactions in page object methods

## Integration Points

- Appium Server: Running on port 4723
- Android Emulator: Required for test execution
- WebDriverIO Services: Using built-in Appium service

## Testing Guidelines

- Tests use Mocha framework with BDD style
- Default timeout: 60000ms for test execution
- Retries configured at connection level

For modifications, ensure you:

1. Follow the Page Object pattern for new page objects
2. Use TypeScript for all new code
3. Maintain async/await pattern for WebDriverIO commands
4. Update selectors when app UI changes
