// Toggle Sidebar on Mobile
document.querySelector('.sidebar-header').addEventListener('click', function() {
    if (window.innerWidth <= 992) {
        const sidebar = document.querySelector('.sidebar');
        sidebar.style.width = sidebar.style.width === '250px' ? '70px' : '250px';
    }
});

// Mark notifications as read
document.querySelector('.notifications').addEventListener('click', function() {
    this.querySelector('.notification-count').style.display = 'none';
});

// Task completion toggle
document.querySelectorAll('.task-checkbox input').forEach(checkbox => {
    checkbox.addEventListener('change', function() {
        const taskItem = this.closest('li');
        if (this.checked) {
            taskItem.style.opacity = '0.6';
            taskItem.querySelector('.task-info h4').style.textDecoration = 'line-through';
        } else {
            taskItem.style.opacity = '1';
            taskItem.querySelector('.task-info h4').style.textDecoration = 'none';
        }
    });
});

// Email read/unread toggle
document.querySelectorAll('.emails-list li').forEach(email => {
    email.addEventListener('click', function() {
        this.classList.toggle('unread');
    });
});

// Quick action buttons
document.querySelectorAll('.quick-action-btn').forEach(button => {
    button.addEventListener('click', function() {
        alert(`"${this.querySelector('span').textContent}" action clicked!`);
    });
});

// Responsive adjustments
window.addEventListener('resize', function() {
    const sidebar = document.querySelector('.sidebar');
    if (window.innerWidth > 992) {
        sidebar.style.width = '250px';
    } else {
        sidebar.style.width = '70px';
    }
});