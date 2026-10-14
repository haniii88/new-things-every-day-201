```javascript
function dailyLog201() {
  const today = new Date("2026-10-14");

  const tasks = [
    { name: "Design UI", completed: true, due: "2026-10-12" },
    { name: "Build API", completed: false, due: "2026-10-13" },
    { name: "Write Tests", completed: false, due: "2026-10-17" },
    { name: "Update Docs", completed: true, due: "2026-10-14" },
  ];

  const completed = tasks.filter(task => task.completed);
  const overdue = tasks.filter(
    task => !task.completed && new Date(task.due) < today
  );

  const progress = Math.round(
    (completed.length / tasks.length) * 100
  );

  console.log("=== Project Progress Report ===");
  console.log(`Total Tasks: ${tasks.length}`);
  console.log(`Completed: ${completed.length}`);
  console.log(`Progress: ${progress}%`);
  console.log(`Overdue Tasks: ${overdue.length}`);

  overdue.forEach(task => {
    console.log(`⚠️ Overdue: ${task.name}`);
  });

  console.log(
    progress === 100
      ? "🎉 All tasks completed!"
      : "💪 Keep moving forward!"
  );
}

dailyLog201();
```
