# Dynamic Routes

## Download Starter Code (Optional)
If you’re NOT continuing from the previous lesson, you can download, install, and run the starter code for this lesson below. 

    npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn/tree/master/basics/dynamic-routes-starter"


## Page Path Depends on External Data

In the previous lesson, we covered the case where the page content depends on external data. We used getStaticProps to fetch required data to render the index page.

![](https://nextjs.org/static/images/learn/dynamic-routes/page-path-external-data.png)


### How to Statically Generate Pages with Dynamic Routes

In our case, we want to create dynamic routes for blog posts:

* We want each post to have the path /posts/<id>, where <id> is the name of the markdown file under the top-level posts directory.
* Since we have ssg-ssr.md and pre-rendering.md, we’d like the paths to be /posts/ssg-ssr and /posts/pre-rendering.

### Overview of the Steps

We can do this by taking the following steps. You don’t have to make these changes yet — we’ll do it all on the next page.

Here’s a graphic summary of what we just talked about:

![](https://nextjs.org/static/images/learn/dynamic-routes/how-to-dynamic-routes.png)

## Implement getStaticPaths
First, let’s set up the files:

* Create a file called [id].js inside the pages/posts directory.
* Also, remove first-post.js inside the pages/posts directory — we’ll no longer use this.

Then, open pages/posts/[id].js in your editor and paste the following code. We’ll fill in ... later:

import Layout from '../../components/layout'

    export default function Post() {
    return <Layout>...</Layout>
    }

Then, open lib/posts.js and add the following getAllPostIds function at the bottom. It will return the list of file names (excluding .md) in the posts directory:

    export function getAllPostIds() {
    const fileNames = fs.readdirSync(postsDirectory)

    // Returns an array that looks like this:
    // [
    //   {
    //     params: {
    //       id: 'ssg-ssr'
    //     }
    //   },
    //   {
    //     params: {
    //       id: 'pre-rendering'
    //     }
    //   }
    // ]
    return fileNames.map(fileName => {
        return {
        params: {
            id: fileName.replace(/\.md$/, '')
        }
        }
    })
    }


Important: The returned list is not just an array of strings — it must be an array of objects that look like the comment above. Each object must have the params key and contain an object with the id key (because we’re using [id] in the file name). Otherwise, getStaticPaths will fail.

    import { getAllPostIds } from '../../lib/posts'

    export async function getStaticPaths() {
    const paths = getAllPostIds()
    return {
        paths,
        fallback: false
    }
    }


# Deploying Your Next.js App

## Download Starter Code (Optional)

If you’re NOT continuing from the previous lesson, you can download, install, and run the starter code for this lesson below. This sets up a nextjs-blog directory such that it’s identical to the result of the previous lesson.

Again, this is NOT necessary if you’ve just finished the previous lesson.

    npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn/tree/master/basics/basics-final"
