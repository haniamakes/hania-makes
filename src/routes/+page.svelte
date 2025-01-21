<script lang="ts">
    let currentDate = new Date();

    const updateDate = () => {
        currentDate = new Date();
    };

    const interval = setInterval(updateDate, 1000);

    const formatDate = (date: Date) => {
        // Array of weekday names
        const weekdays = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
        
        // Array of month names
        const months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
        
        // Get the weekday, month, day, and year
        const weekday = weekdays[date.getDay()];
        const month = months[date.getMonth()];
        const day = date.getDate();
        const year = date.getFullYear();
        
        // Format the date as "Sunday, 7 January, 2024"
        return `${weekday}, ${day} ${month} ${year}`;
        }

    import { onDestroy } from 'svelte';
    onDestroy(() => {
        clearInterval(interval);
    });
</script>
<div class="newspaper">
    <div class="grainy-text title">Hania Dziurdzik</div>
    <div id="tagline" class="grainy-text subtitle-lg fulljustify">A Personal Website</div>
    <hr/>
    <hr style="margin-bottom:16px;"/>
    <div class="newspaper-body">
        <div class="row">
            <div>
                {formatDate(currentDate)}
            </div>
            <div style="text-align: right;">
                Chicago, IL
            </div>
        </div>
        
        <div class="row">
            <div class="column-lg">
                <div>
                    <strong>I  am  a</strong> full-stack software engineer, rugby player, cat mom, knitter, quilter, seamstress, maker. I have experience in AI and finance, a knack for creativity, and I strive for efficiency and effectiveness without sacrificing attention to detail.
                </div>
                <div class="social-icons">
                    <a target="_blank" aria-label="github" href="https://github.com/hdziurdzik" class="social-icon"><i class="fab fa-github"></i></a>
                    <a target="_blank" aria-label="instagram" href="https://www.instagram.com/hdziurdzik/" class="social-icon"><i class="fab fa-instagram"></i></a>
                    <a target="_blank" aria-label="linkedin" href="https://www.linkedin.com/in/hdziurdzik/" class="social-icon"><i class="fab fa-linkedin-in"></i></a>
                </div>
            </div>
            <div class="column-med">
                <img class="old-image" src="/hania_headshot.jpg" alt="Headshot of me" />
            </div>
            <div class="column border-left">
                <div class="blog-link"> Click <strong><a href="/projects">here</a></strong> to see the projects I'm working on this week</div>
                <div class="blog-link-inverted"> Click <strong><a href="/about">here</a></strong> for a closer look at my resume</div>
                <div class="blog-link">Stay tuned for more!</div>
            </div>
        </div>
    </div>
</div>
