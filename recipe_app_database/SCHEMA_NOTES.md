This container is PostgreSQL-backed and is started by startup.sh (see manifest).

No db_connection.txt was found in the workspace; per project rules, create one before applying SQL changes.

Intended schema for the Recipe Hub backend (tables):
- users (id, email, password_hash, display_name, is_admin, created_at)
- recipes (id, title, description, image_url, ingredients, instructions, prep_minutes, cook_minutes, servings, is_public, is_flagged, author_id, created_at, updated_at)
- categories (id, name)
- tags (id, name)
- recipe_categories (recipe_id, category_id)
- recipe_tags (recipe_id, tag_id)
- favorites (id, user_id, recipe_id, created_at)
- shopping_list_items (id, user_id, text, is_checked, created_at)
- moderation_logs (id, admin_user_id, action, recipe_id, note, created_at)

The backend uses SQLAlchemy models and expects DATABASE_URL to be configured.
