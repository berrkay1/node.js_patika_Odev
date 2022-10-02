# node.js_patika_Odev
let posts = [
    {
        title: "Post 1",
        author: "  Author 1",
        content: "Content 1",
    },
    {
        title: "Post 2",
        author: "  Author 2",
        content: "Content 2",
    },
    {
        title: "Post 3",
        author: "  Author 3",
        content: "Content 3",
    },

];


const getPosts = () => {
    return new Promise((resolve, reject) => {
        if (posts) {
            posts.map(item => {
                console.log(item.title);
            })
            resolve(posts);
        } else {
            reject("hata oluştu")
        }
    })
}

const addPost = (newPost) => {
    return new Promise((resolve, reject) => {
        if (newPost) {
            posts.push(newPost);
            resolve(posts);
        } else {
            reject("post eklenmedi")
        }
    })

}


const listPosts = async () => {
    try{
        await addPost({
            title: "Post 10",
            author: "  Author 10",
            content: "Content 10",
        });
        console.log(await getPosts());

    }catch (err) {
        console.log(err);
    }
}

listPosts();
