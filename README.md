# 🚀 Serverless Task Manager

A modern, fully serverless To-Do app built with **AWS Lambda**, **API Gateway**, **DynamoDB**, and **S3**.  
Drag, reorder, add, complete, and delete tasks with a smooth, responsive UI.

## Live Demo

[Access the app here](https://dz6cx3cobt6px.cloudfront.net)

---

## Features

- Add new tasks
- Mark tasks as completed
- Delete tasks
- Filter tasks: All / Active / Completed
- Drag-and-drop to reorder tasks
- Fully serverless architecture (no backend server to maintain)

---

## Architecture

1. **Frontend**: Hosted on S3 as a static website.
2. **Backend**: AWS Lambda functions connected via API Gateway.
3. **Database**: DynamoDB storing tasks with `taskId`, `title`, `completed`, and `order`.
4. **CORS** enabled on API Gateway to allow frontend requests.
5. Smooth drag-and-drop with persistent ordering.

---

## AWS Services Used

- **S3**: Static frontend hosting
- **DynamoDB**: Tasks storage
- **API Gateway**: REST API for frontend communication
- **Lambda**: Serverless backend for CRUD and reordering operations
- **CloudWatch**: Logs for Lambda monitoring

---

## Setup Steps

1. **DynamoDB**
   - Create table `ToDoTasks` with:
     - Partition key: `taskId` (String)
     - Attributes: `title` (String), `completed` (Boolean), `order` (Number)

2. **Lambda Functions**
   - `createTask`: Adds new tasks
   - `updateTask`: Updates task completion or order
   - `deleteTask`: Deletes tasks
   - **Use Python** or Node.js; integrate with DynamoDB

3. **API Gateway**
   - Create REST API `/tasks` with methods:
     - `GET` → List tasks
     - `POST` → Add task
     - `PATCH` → Update task
     - `DELETE` → Delete task
   - Enable **CORS** for all methods

4. **S3 Frontend**
   - Upload `index.html` (provided)
   - Enable static website hosting
   - Set `index.html` as the default document

---

## How to Use

1. Open the live app link in a browser.
2. Add tasks using the input box.
3. Mark tasks as completed using checkboxes.
4. Delete tasks using the red button.
5. Drag and drop tasks to reorder them.
6. Use filters to view All, Active, or Completed tasks.

---

## Tech Stack

- **Frontend**: HTML, CSS, JavaScript
- **Backend**: AWS Lambda (Python or Node.js)
- **Database**: DynamoDB
- **Hosting**: AWS S3
- **API Gateway**: REST API
- **Monitoring**: CloudWatch

---

## License

MIT License

---

## Notes

- Drag-and-drop ordering persists automatically.
- All backend operations are serverless and scalable.
- Check **CloudWatch Logs** for debugging Lambda issues.
