# pos-keepalive

Pings the free Render web service of the Retail POS every 10 minutes so it
does not spin down (Render sleeps after 15 minutes of no traffic, causing a
~50s cold start).

- keep-awake.yml - scheduled every 10 minutes, GETs /health, fails if not 200.
- monthly-activity.yml - commits a timestamp on the 1st of each month so
  GitHub does not auto-disable scheduled workflows after 60 idle days.

Target: https://retail-pos-0s66.onrender.com/health
