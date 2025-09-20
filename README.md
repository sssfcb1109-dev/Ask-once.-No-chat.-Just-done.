# Ask-once.-No-chat.-Just-done.
 (cd "$(git rev-parse --show-toplevel)" && git apply --3way <<'EOF' 
diff --git a/README.md b/README.md
index fade6d0910f8b9a2b8fa4fdf699ff18477d49df0..819ecc39f47f525c310cbb2cc2727efc94e1d076 100644
--- a/README.md
+++ b/README.md
@@ -1,19 +1,30 @@
 # TaskSimplifier
 
-This repository provides a minimal Flask API for demonstration.
+This repository provides a minimal Flask API for demonstrating a "one-shot" task
+automation flow.
 
 ## Usage
 
 1. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
 2. Start the server:
    ```bash
    python app.py
    ```
-3. Send a POST request with JSON payload:
+3. Send a POST request to `/one-shot-plan` with a JSON payload such as:
    ```json
-   {"from": "alice@example.com", "subject": "Hello", "body": "Hi there"}
+   {
+     "scenario": "Need help with UCLA post-arrival orientation",
+     "preferred_name": "Alex",
+     "term": "Fall 2024"
+   }
    ```
-   to `/reply` to receive a fixed automated response.
+   The API responds with a single confirmation sheet that summarizes assumptions,
+   required inputs, proposed automations, and reference links for the UCLA
+   post-arrival orientation flow.
+
+4. Provide any other scenario description to receive a placeholder response that
+   explains what extra detail the agent still needs before it can build a
+   confirmation sheet.
 
EOF
)
