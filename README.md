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

----------------

<?php if (have_rows('letter_page')): ?> <?php /* flexible field group */ ?>
    <?php while (have_rows('letter_page')): the_row(); ?>
        <?php if (get_row_layout() == 'text_field_text'): ?>
            <?php get_template_part('template-parts/text_field'); ?>

        <?php elseif (get_row_layout() == 'text_editor_editor'): ?>
            <?php get_template_part('template-parts/text_editor'); ?>
        <?php endif; ?>
    <?php endwhile; ?>
<?php endif; ?>


------
functions.php

function register_my_menu() {
    register_nav_menu('header_menu', __('Головне меню'));
}
add_action('after_setup_theme', 'register_my_menu');

header.php
<?php
        wp_nav_menu(array(
            'theme_location' => 'header_menu',
            'menu_class' => 'header-menu',
            'container' => 'nav',
        ));
        ?>
