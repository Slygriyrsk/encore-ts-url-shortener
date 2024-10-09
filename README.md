# URL Shortener with Encore.ts

This project is a URL shortener service built with Encore.ts. It allows users to create short, easy-to-share links for long URLs.

## Table of Contents

- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Development](#development)
- [Deployment](#deployment)
- [Testing](#testing)
- [Docker](#docker)

## Features

- Shorten long URLs to compact, shareable links
- Retrieve original URLs using shortened IDs
- Built with Encore.ts for efficient backend development
- Deployable to Encore's development cloud

## Getting Started

### Prerequisites

- [Encore](https://encore.dev/docs/install) installed on your system
- Node.js and npm (for local development)
- Docker (optional, for running containers)

### Installation

1. Create a new Encore application using this template:

   ```bash
   encore app create encore-ts-url-shortener --example=ts/empty
   ```

2. Navigate to the project directory:

   ```bash
   cd encore-ts-url-shortener
   ```

3. Install dependencies:

   ```bash
   npm install
   ```

## Usage

To create a shortened URL:

```bash
curl -X POST https://staging-encore-url-shortener-rd32.encr.app/url -d "{\"url\": \"https://twitter.com/repatriation_23\"}" -H "Content-type: application/json"
```

Example response:
```json
{"id":"BLGZchQY","url":"https://twitter.com/repatriation_23"}
```

To retrieve the original URL:

```bash
curl https://staging-encore-url-shortener-rd32.encr.app/url/BLGZchQY
```

Example response:
```json
{"url":"https://twitter.com/repatriation_23","id":"BLGZchQY"}
```

## Development

To run the application locally:

```bash
encore run
```

While `encore run` is running, open [http://localhost:9400/](http://localhost:9400/) to view Encore's [local developer dashboard](https://encore.dev/docs/observability/dev-dash).

![Local Development](https://github.com/user-attachments/assets/68f729f9-c3c3-48da-83ce-779b7dceb7f4)

## Deployment

To deploy your application to a staging environment in Encore's free development cloud:

```bash
git add -A .
git commit -m 'Commit message'
git push encore
```

After pushing, head over to the [Cloud Dashboard](https://app.encore.dev) to monitor your deployment and find your production URL.

## Testing

Run tests using the following command:

```bash
encore test
```

![Encore Dashboard](https://github.com/user-attachments/assets/3222cb22-d429-40fd-9148-73bd105b7f6e)

## Docker

The project uses Docker containers for the database and other services. Here's a view of the Docker containers running:

![Docker Containers](https://github.com/user-attachments/assets/17ed9ef1-1286-4a53-bc05-3e204c168add)

This image shows the SQL database container and other related containers used in the project.

---

For more information on Encore and its features, visit the [Encore Documentation](https://encore.dev/docs).
```
