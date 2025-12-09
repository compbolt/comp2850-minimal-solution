


fix 1: Edit bttton 
old code:
private suspend fun ApplicationCall.handleEditTask(store: TaskStore) {
    val id = parameters["id"] ?: run {
        respond(HttpStatusCode.BadRequest)
        return
    }

    val task = store.getById(id)
    if (task == null) {
        respond(HttpStatusCode.NotFound)
        return
    }

    if (isHtmxRequest()) {
        // HTMX: return inline edit fragment
        val html = renderTemplate("tasks/_edit.peb", mapOf("task" to task.toPebbleContext()))
        respondText(html, ContentType.Text.Html)
    } else {
        // No-JS: Render full page with 'editingTaskId' in context
        // This ensures the list, search, and page position are maintained
        val query = requestedQuery()
        val page = requestedPage()
        val paginated = paginateTasks(store, query, page)
        
        // Convert ID to Int to match template logic (assuming ID is integer-based in Pebble)
        val editingIdInt = id.toIntOrNull() ?: -1

        val context = paginated.context + mapOf("editingTaskId" to editingIdInt)
        val html = renderTemplate("tasks/index.peb", context)
        respondText(html, ContentType.Text.Html)
    }
}
new code:
private suspend fun ApplicationCall.handleEditTask(store: TaskStore) {
    val id = parameters["id"] ?: run {
        respond(HttpStatusCode.BadRequest)
        return
    }

    val task = store.getById(id)
    if (task == null) {
        respond(HttpStatusCode.NotFound)
        return
    }

    if (isHtmxRequest()) {
        // HTMX: return inline edit fragment
        // Ensure toPebbleContext() is imported if it's an extension function
        val html = renderTemplate("tasks/_edit.peb", mapOf("task" to task.toPebbleContext()))
        respondText(html, ContentType.Text.Html)
    } else {
        // No-JS: Render full page
        val query = requestedQuery()
        val page = requestedPage()
        val paginated = paginateTasks(store, query, page)
        
        // FIX: The ID is a String (UUID), so passing it as a String is correct.
        // We cast the map explicitly to ensure type safety if needed.
        val context: Map<String, Any> = paginated.context + mapOf("editingTaskId" to id)
        
        val html = renderTemplate("tasks/index.peb", context)
        respondText(html, ContentType.Text.Html)
    }
}


fix 2: colour buttons



fix 3: highlight keyboard focus better


