<?php 
$c_phone = get_field('c_phone', 'option'); 
$c_email = get_field('c_email', 'option'); 

if ($c_phone): ?>
    <p>Телефон: <?php echo esc_html($c_phone); ?></p>
<?php endif; ?>

<?php if ($c_email): ?>
    <p>Email: <?php echo esc_html($c_email); ?></p>
<?php endif; ?>

-------------------

<?php
// Отримуємо поточний URL
$current_url = $_SERVER['REQUEST_URI'];

// Перевіряємо, чи є в URL "/en/"
if (strpos($current_url, '/en/') !== false): ?>
    <button>Car</button>
<?php else: ?>
    <button>Машина</button>
<?php endif; ?>
