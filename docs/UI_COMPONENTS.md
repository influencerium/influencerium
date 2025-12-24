# Influencerium UI Components

**Reusable Component Library**

---

## 📋 Table of Contents

1. [Overview](#overview)
2. [Button Components](#button-components)
3. [Form Components](#form-components)
4. [Card Components](#card-components)
5. [Navigation Components](#navigation-components)
6. [Modal Components](#modal-components)
7. [Alert Components](#alert-components)
8. [Badge Components](#badge-components)

---

## 🎯 Overview

The Influencerium UI Component Library provides a collection of reusable, accessible, and consistent components for building the platform.

### Component Principles

- **Reusable** - Use across the entire application
- **Accessible** - WCAG 2.1 AA compliant
- **Responsive** - Work on all screen sizes
- **Consistent** - Follow design system guidelines
- **Documented** - Clear usage examples

---

## 🔘 Button Components

### Primary Button

**Usage:** Main actions, CTAs

```jsx
<Button variant="primary" size="md">
  Click Me
</Button>
```

**Props:**
- `variant`: primary, secondary, danger
- `size`: sm, md, lg
- `disabled`: boolean
- `loading`: boolean
- `onClick`: function

**Styles:**
- Background: #0066CC
- Text: White
- Padding: 12px 24px
- Border Radius: 6px

### Secondary Button

**Usage:** Alternative actions

```jsx
<Button variant="secondary" size="md">
  Cancel
</Button>
```

### Danger Button

**Usage:** Destructive actions

```jsx
<Button variant="danger" size="md">
  Delete
</Button>
```

### Button Sizes

| Size | Padding | Font Size |
|------|---------|-----------|
| **sm** | 8px 16px | 14px |
| **md** | 12px 24px | 16px |
| **lg** | 16px 32px | 18px |

---

## 📝 Form Components

### Input Field

**Usage:** Text input

```jsx
<Input
  type="text"
  placeholder="Enter text"
  value={value}
  onChange={handleChange}
  error={error}
/>
```

**Props:**
- `type`: text, email, password, number, etc.
- `placeholder`: string
- `value`: string
- `onChange`: function
- `error`: string
- `disabled`: boolean
- `required`: boolean

### Textarea

**Usage:** Multi-line text input

```jsx
<Textarea
  placeholder="Enter message"
  rows={4}
  value={value}
  onChange={handleChange}
/>
```

### Select Dropdown

**Usage:** Choose from options

```jsx
<Select
  options={[
    { value: 'creator', label: 'Creator' },
    { value: 'brand', label: 'Brand' }
  ]}
  value={value}
  onChange={handleChange}
/>
```

### Checkbox

**Usage:** Multiple selections

```jsx
<Checkbox
  label="I agree to terms"
  checked={checked}
  onChange={handleChange}
/>
```

### Radio Button

**Usage:** Single selection

```jsx
<Radio
  name="userType"
  value="creator"
  label="Creator"
  checked={checked}
  onChange={handleChange}
/>
```

### Date Picker

**Usage:** Select date

```jsx
<DatePicker
  value={date}
  onChange={handleChange}
  minDate={minDate}
  maxDate={maxDate}
/>
```

---

## 🎴 Card Components

### Basic Card

**Usage:** Container for content

```jsx
<Card>
  <Card.Header>
    <h3>Card Title</h3>
  </Card.Header>
  <Card.Body>
    <p>Card content</p>
  </Card.Body>
  <Card.Footer>
    <Button>Action</Button>
  </Card.Footer>
</Card>
```

### Campaign Card

**Usage:** Display campaign information

```jsx
<CampaignCard
  campaign={campaign}
  onApply={handleApply}
  onView={handleView}
/>
```

**Displays:**
- Campaign title
- Budget
- Timeline
- Status
- Apply button

### Creator Card

**Usage:** Display creator profile

```jsx
<CreatorCard
  creator={creator}
  onContact={handleContact}
  onView={handleView}
/>
```

**Displays:**
- Creator name
- Avatar
- Niche
- Followers
- Rating
- Contact button

### Brand Card

**Usage:** Display brand profile

```jsx
<BrandCard
  brand={brand}
  onContact={handleContact}
  onView={handleView}
/>
```

---

## 🧭 Navigation Components

### Navbar

**Usage:** Top navigation

```jsx
<Navbar>
  <Navbar.Brand>Influencerium</Navbar.Brand>
  <Navbar.Menu>
    <Navbar.Item href="/">Home</Navbar.Item>
    <Navbar.Item href="/campaigns">Campaigns</Navbar.Item>
    <Navbar.Item href="/profile">Profile</Navbar.Item>
  </Navbar.Menu>
  <Navbar.User>
    <UserMenu />
  </Navbar.User>
</Navbar>
```

### Sidebar

**Usage:** Side navigation

```jsx
<Sidebar>
  <Sidebar.Item icon="home" href="/">Home</Sidebar.Item>
  <Sidebar.Item icon="campaigns" href="/campaigns">Campaigns</Sidebar.Item>
  <Sidebar.Item icon="messages" href="/messages">Messages</Sidebar.Item>
  <Sidebar.Item icon="settings" href="/settings">Settings</Sidebar.Item>
</Sidebar>
```

### Breadcrumb

**Usage:** Navigation path

```jsx
<Breadcrumb>
  <Breadcrumb.Item href="/">Home</Breadcrumb.Item>
  <Breadcrumb.Item href="/campaigns">Campaigns</Breadcrumb.Item>
  <Breadcrumb.Item active>Campaign Details</Breadcrumb.Item>
</Breadcrumb>
```

### Pagination

**Usage:** Navigate pages

```jsx
<Pagination
  currentPage={page}
  totalPages={totalPages}
  onPageChange={handlePageChange}
/>
```

---

## 🪟 Modal Components

### Basic Modal

**Usage:** Dialog box

```jsx
<Modal isOpen={isOpen} onClose={handleClose}>
  <Modal.Header>
    <h2>Modal Title</h2>
  </Modal.Header>
  <Modal.Body>
    <p>Modal content</p>
  </Modal.Body>
  <Modal.Footer>
    <Button onClick={handleClose}>Cancel</Button>
    <Button variant="primary" onClick={handleConfirm}>Confirm</Button>
  </Modal.Footer>
</Modal>
```

### Confirmation Modal

**Usage:** Confirm action

```jsx
<ConfirmModal
  isOpen={isOpen}
  title="Delete Campaign?"
  message="This action cannot be undone."
  onConfirm={handleDelete}
  onCancel={handleCancel}
/>
```

### Alert Modal

**Usage:** Show alert

```jsx
<AlertModal
  isOpen={isOpen}
  type="success"
  title="Success!"
  message="Campaign created successfully."
  onClose={handleClose}
/>
```

---

## 🚨 Alert Components

### Alert Box

**Usage:** Display messages

```jsx
<Alert type="success" title="Success!" message="Operation completed." />
<Alert type="error" title="Error!" message="Something went wrong." />
<Alert type="warning" title="Warning!" message="Please review." />
<Alert type="info" title="Info!" message="Additional information." />
```

### Toast Notification

**Usage:** Temporary notification

```jsx
<Toast
  type="success"
  message="Campaign created successfully!"
  duration={3000}
/>
```

---

## 🏷️ Badge Components

### Status Badge

**Usage:** Show status

```jsx
<Badge status="active">Active</Badge>
<Badge status="pending">Pending</Badge>
<Badge status="completed">Completed</Badge>
```

### Category Badge

**Usage:** Show category

```jsx
<Badge category="technology">Technology</Badge>
<Badge category="fashion">Fashion</Badge>
<Badge category="lifestyle">Lifestyle</Badge>
```

### Rating Badge

**Usage:** Show rating

```jsx
<Badge rating={4.5}>4.5 ⭐</Badge>
```

---

## 📊 Component States

### Loading State

```jsx
<Button loading>Loading...</Button>
<Input disabled placeholder="Loading..." />
```

### Disabled State

```jsx
<Button disabled>Disabled</Button>
<Input disabled />
```

### Error State

```jsx
<Input error="Email is required" />
<Alert type="error" message="Validation failed" />
```

### Success State

```jsx
<Alert type="success" message="Operation successful" />
<Badge status="completed">Completed</Badge>
```

---

## 🎨 Component Customization

### Theme Props

```jsx
<Button theme="dark">Dark Button</Button>
<Button theme="light">Light Button</Button>
```

### Size Variants

```jsx
<Button size="sm">Small</Button>
<Button size="md">Medium</Button>
<Button size="lg">Large</Button>
```

### Color Variants

```jsx
<Button color="primary">Primary</Button>
<Button color="secondary">Secondary</Button>
<Button color="danger">Danger</Button>
```

---

## 📱 Responsive Components

All components are responsive and work on:
- Mobile (320px - 640px)
- Tablet (641px - 1024px)
- Desktop (1025px+)

---

## 📞 Support

For component questions:
- **GitHub:** https://github.com/influencerium/influencerium
- **Email:** support@influencerium.com

---

**Last Updated:** December 24, 2025  
**Version:** 1.0.0  
**Status:** ✅ Complete
