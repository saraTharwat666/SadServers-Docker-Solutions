Markdown

# 🌐 Scenario: Auderghem - Containers Miscommunication

![Docker](https://media.giphy.com/media/SS8CV2rQdlYNLtBCiF/giphy.gif)

## 📝 Challenge Description
The goal is to fix a broken Nginx reverse proxy configuration. The Nginx container is supposed to route traffic to two backend containers, `statichtml1` and `statichtml2`, based on the URL path, but the redirection is currently failing.

**Requirements:**
- `curl http://localhost/1` must route to `statichtml1`.
- `curl http://localhost/2` must route to `statichtml2`.
- Containers must not be stopped or removed; only restarts are allowed.

---

## 🔍 Investigation & Logic
In a Docker environment, containers communicate using an internal network where the **Container Name** acts as the hostname (Docker DNS). 

The issue typically stems from one of the following:
1. **Upstream Mismatch:** The Nginx configuration might be trying to reach the backends via `localhost` or incorrect IP addresses instead of using the Docker container names.
2. **Path Configuration:** The `location` blocks in the Nginx config might not be correctly appending or stripping paths when forwarding to the static HTML services.



By inspecting the Nginx configuration file (usually found at `/etc/nginx/conf.d/default.conf` or `/etc/nginx/nginx.conf`), we can ensure the `proxy_pass` directives are correctly pointing to `http://statichtml1:80` and `http://statichtml2:80`.

---

## 🛠️ The Fix

### 1. Identify and Edit Configuration
Inspected the Nginx configuration inside the container:
```bash
docker exec -it nginx cat /etc/nginx/conf.d/default.conf
Corrected the location blocks to ensure proper routing:

Location /1: Points to http://statichtml1:80/

Location /2: Points to http://statichtml2:80/
```


2. Apply Changes
Since we cannot remove the container, we reload the Nginx configuration or restart the container:

```Bash

docker restart nginx
# Or more efficiently:
docker exec nginx nginx -s reload
```


✅ Verification
Testing the proxy routing:

```Bash

curl http://localhost/1 # Expected: HelloWorld;1
curl http://localhost/2 # Expected: HelloWorld;2
```




























