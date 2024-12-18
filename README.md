# Next.js 15 useEffect Cleanup Issue

This repository demonstrates a bug in a Next.js 15 application where a `useEffect` hook's cleanup function doesn't work as expected when navigating away from a page.  The `useEffect` hook is used to set up an interval counter, which continues to run even after leaving the component, resulting in unexpected behavior.

## Bug Description:
The counter on the `/about` page continues incrementing even after navigating away from the page to another route. This is likely due to the interval not being cleared properly when the component unmounts.

## How to Reproduce:
1. Clone this repository.
2. Install dependencies using `npm install`.
3. Run the development server using `npm run dev`.
4. Navigate to `/about`.
5. Navigate away from `/about` to another route (e.g., `/`).
6. Observe that the counter on the `/about` page continues to increment in the background, even though you're no longer on the page. This indicates a memory leak and incorrect cleanup function behavior.

## Solution:
The solution involves carefully inspecting the cleanup function within the `useEffect` hook. There might be issues with how the interval is cleared or when the cleanup function is executed.

This example demonstrates a common problem with useEffect and how to correctly clear intervals or timeouts to prevent memory leaks.