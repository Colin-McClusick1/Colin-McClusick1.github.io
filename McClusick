/**
 * Colin McClusick AI Consulting Website
 * Main JavaScript file for interactive functionality
 */

// ============================================
// Utility Functions
// ============================================

const utils = {
    // Show element with animation
    show(element, displayStyle = 'block') {
        if (element) {
            element.style.display = displayStyle;
            setTimeout(() => element.style.opacity = '1', 10);
        }
    },
    
    // Hide element with animation
    hide(element) {
        if (element) {
            element.style.opacity = '0';
            setTimeout(() => element.style.display = 'none', 300);
        }
    },
    
    // Disable button with loading state
    setButtonLoading(button, loadingText = 'Loading...') {
        if (!button) return null;
        const originalText = button.textContent;
        button.textContent = loadingText;
        button.disabled = true;
        return originalText;
    },
    
    // Reset button to original state
    resetButton(button, originalText) {
        if (button && originalText) {
            button.textContent = originalText;
            button.disabled = false;
        }
    }
};

// ============================================
// Mobile Menu Handler
// ============================================

const mobileMenu = {
    toggle: null,
    menu: null,
    spans: null,
    
    init() {
        this.toggle = document.querySelector('.mobile-menu-toggle');
        this.menu = document.querySelector('.nav-menu');
        
        if (!this.toggle || !this.menu) return;
        
        this.spans = this.toggle.querySelectorAll('span');
        this.bindEvents();
    },
    
    bindEvents() {
        // Toggle menu on button click
        this.toggle.addEventListener('click', () => this.toggleMenu());
        
        // Close menu when clicking nav links
        const navLinks = this.menu.querySelectorAll('a');
        navLinks.forEach(link => {
            link.addEventListener('click', () => this.closeMenu());
        });
        
        // Close menu when clicking outside
        document.addEventListener('click', (e) => {
            if (this.menu.classList.contains('active') && 
                !this.menu.contains(e.target) && 
                !this.toggle.contains(e.target)) {
                this.closeMenu();
            }
        });
    },
    
    toggleMenu() {
        this.menu.classList.toggle('active');
        this.animateHamburger(this.menu.classList.contains('active'));
    },
    
    closeMenu() {
        this.menu.classList.remove('active');
        this.animateHamburger(false);
    },
    
    animateHamburger(isOpen) {
        if (isOpen) {
            this.spans[0].style.transform = 'rotate(45deg) translateY(7px)';
            this.spans[1].style.opacity = '0';
            this.spans[2].style.transform = 'rotate(-45deg) translateY(-7px)';
        } else {
            this.spans[0].style.transform = 'none';
            this.spans[1].style.opacity = '1';
            this.spans[2].style.transform = 'none';
        }
    }
};

// ============================================
// Contact Form Handler
// ============================================

const contactForm = {
    form: null,
    status: null,
    
    init() {
        this.form = document.getElementById('contactForm');
        if (!this.form) return;
        
        this.status = document.getElementById('formStatus');
        this.bindEvents();
    },
    
    bindEvents() {
        this.form.addEventListener('submit', (e) => this.handleSubmit(e));
    },
    
    async handleSubmit(e) {
        e.preventDefault();
        
        const submitButton = this.form.querySelector('button[type="submit"]');
        const formData = new FormData(this.form);
        const originalText = utils.setButtonLoading(submitButton, 'Sending...');
        
        try {
            // Simulate API call (replace with actual endpoint)
            await this.simulateSubmit(formData);
            
            this.showSuccess();
            this.form.reset();
        } catch (error) {
            this.showError(error.message);
        } finally {
            utils.resetButton(submitButton, originalText);
        }
    },
    
    simulateSubmit(formData) {
        return new Promise((resolve) => {
            setTimeout(() => resolve(), 1000);
        });
        
        // In production, replace with:
        /*
        return fetch('YOUR_FORM_ENDPOINT', {
            method: 'POST',
            body: formData
        }).then(response => {
            if (!response.ok) throw new Error('Network response was not ok');
            return response.json();
        });
        */
    },
    
    showSuccess() {
        if (!this.status) return;
        
        this.status.className = 'form-status success';
        this.status.textContent = 'Thank you! Your message has been sent. I\'ll get back to you within 24 hours.';
        this.status.style.display = 'block';
        
        // Auto-hide after 5 seconds
        setTimeout(() => utils.hide(this.status), 5000);
    },
    
    showError(message = 'Sorry, there was an error. Please try again.') {
        if (!this.status) return;
        
        this.status.className = 'form-status error';
        this.status.textContent = message;
        this.status.style.display = 'block';
        
        // Auto-hide after 5 seconds
        setTimeout(() => utils.hide(this.status), 5000);
    }
};

// ============================================
// Newsletter Form Handler
// ============================================

const newsletterHandler = {
    init() {
        const forms = document.querySelectorAll('.newsletter-form');
        forms.forEach(form => this.bindForm(form));
    },
    
    bindForm(form) {
        form.addEventListener('submit', async (e) => {
            e.preventDefault();
            
            const email = form.querySelector('input[type="email"]').value;
            const submitButton = form.querySelector('button[type="submit"]');
            const originalText = utils.setButtonLoading(submitButton, 'Subscribing...');
            
            try {
                await this.subscribe(email);
                alert('Thank you for subscribing! Check your email for confirmation.');
                form.reset();
            } catch (error) {
                alert('Error subscribing. Please try again.');
            } finally {
                utils.resetButton(submitButton, originalText);
            }
        });
    },
    
    subscribe(email) {
        return new Promise((resolve) => {
            setTimeout(() => resolve(), 1000);
        });
        
        // In production, replace with:
        /*
        return fetch('YOUR_NEWSLETTER_ENDPOINT', {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify({ email })
        }).then(response => {
            if (!response.ok) throw new Error('Subscription failed');
            return response.json();
        });
        */
    }
};

// ============================================
// Resource Download Handler
// ============================================

const resourceHandler = {
    init() {
        const forms = document.querySelectorAll('.resource-form');
        forms.forEach(form => this.bindForm(form));
    },
    
    bindForm(form) {
        form.addEventListener('submit', async (e) => {
            e.preventDefault();
            
            const email = form.querySelector('input[type="email"]').value;
            const submitButton = form.querySelector('button[type="submit"]');
            const originalText = utils.setButtonLoading(submitButton, 'Sending...');
            
            try {
                await this.sendResource(email);
                alert('Thank you! Check your email for the download link to "5 Ways AI Can Transform Your Sales Operations"');
                form.reset();
            } catch (error) {
                alert('Error sending resource. Please try again.');
            } finally {
                utils.resetButton(submitButton, originalText);
            }
        });
    },
    
    sendResource(email) {
        return new Promise((resolve) => {
            setTimeout(() => resolve(), 1000);
        });
        
        // In production, implement actual email/download service
    }
};

// ============================================
// Calendar Integration
// ============================================

const calendarHandler = {
    init() {
        const calendarLink = document.getElementById('calendarLink');
        if (!calendarLink) return;
        
        calendarLink.addEventListener('click', (e) => {
            e.preventDefault();
            
            // Placeholder alert - replace with actual calendar integration
            alert('Calendar integration would go here. You can use services like Calendly, Cal.com, or similar.');
            
            // In production, open your calendar booking tool:
            // window.open('https://calendly.com/your-link', '_blank');
        });
    }
};

// ============================================
// Smooth Scroll Handler
// ============================================

const smoothScroll = {
    init() {
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', (e) => {
                const href = anchor.getAttribute('href');
                if (href === '#') return;
                
                e.preventDefault();
                const target = document.querySelector(href);
                
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    }
};

// ============================================
// Scroll Animations
// ============================================

const scrollAnimations = {
    observer: null,
    
    init() {
        const options = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        this.observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                    // Unobserve after animation to improve performance
                    this.observer.unobserve(entry.target);
                }
            });
        }, options);
        
        this.observeElements();
    },
    
    observeElements() {
        const animatedElements = document.querySelectorAll(
            '.service-card, .prop-card, .expertise-card, .timeline-item, .faq-item'
        );
        
        animatedElements.forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            this.observer.observe(el);
        });
    }
};

// ============================================
// Initialize All Modules
// ============================================

document.addEventListener('DOMContentLoaded', () => {
    mobileMenu.init();
    contactForm.init();
    newsletterHandler.init();
    resourceHandler.init();
    calendarHandler.init();
    smoothScroll.init();
    scrollAnimations.init();
});
