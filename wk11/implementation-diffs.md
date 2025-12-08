


fix 1: Edit bttton 
old code:
    } else {
        // No-JS: redirect to list (would need edit mode support in index)
        respondRedirect("/tasks")
    }
}


new code:
        val html = call.renderTemplate("tasks/index.peb", mapOf(
            "title" to "Edit Task",
            "tasks" to TaskRepository.all(),
            "editingTaskId" to id
        ))
        call.respondText(html, ContentType.Text.Html)
    }


fix 2: colour buttons



fix 3: highlight keyboard focus better


