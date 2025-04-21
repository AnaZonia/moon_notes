<%*
const today = tp.date.now("YYYY-MM-DD");
const dayOfWeek = tp.date.now("d"); // 0=Sunday, 1=Monday, ..., 6=Saturday

// Calculate days until next Monday
// If today is Monday (1), next Monday is 7 days later
const daysUntilNextMonday = (8 - dayOfWeek) % 7 || 7;

// Get next Monday date
const nextMonday = tp.date.now("YYYY-MM-DD", daysUntilNextMonday);

// Get next Sunday date (6 days after next Monday)
const nextSunday = tp.date.now("YYYY-MM-DD", daysUntilNextMonday + 6);

// Format range string
const startRange = tp.date.now("MMM D, YYYY", daysUntilNextMonday);
const endRange = tp.date.now("MMM D, YYYY", daysUntilNextMonday + 6);
const weekRange = `${startRange} : ${endRange}`;
%>

## <%* tR += weekRange %>

### Sunday, <%* tR += tp.date.now("MMM D, YYYY", daysUntilNextMonday + 6) %>
### Saturday, <%* tR += tp.date.now("MMM D, YYYY", daysUntilNextMonday + 5) %>

### Friday, <%* tR += tp.date.now("MMM D, YYYY", daysUntilNextMonday + 4) %>

### Thursday, <%* tR += tp.date.now("MMM D, YYYY", daysUntilNextMonday + 3) %>

### Wednesday, <%* tR += tp.date.now("MMM D, YYYY", daysUntilNextMonday + 2) %>

### Tuesday, <%* tR += tp.date.now("MMM D, YYYY", daysUntilNextMonday + 1) %>
### Monday, <%* tR += tp.date.now("MMM D, YYYY", daysUntilNextMonday) %>

### Weekly Goals
