from github import Github

def github_personal_assistant():
    # Replace 'your_token' with your GitHub personal access token
    token = 'your_token'
    g = Github(token)

    user = g.get_user()
    print(f"Logged in as {user.login}")

    while True:
        print("\nGitHub Personal Assistant Menu:")
        print("1. List repositories")
        print("2. Create a new repository")
        print("3. Exit")

        choice = input("Enter your choice (1/2/3): ")

        if choice == '1':
            print("\nYour repositories:")
            for repo in user.get_repos():
                print(repo.name)

        elif choice == '2':
            repo_name = input("Enter the new repository name: ")
            user.create_repo(repo_name)
            print(f"Repository '{repo_name}' created successfully!")

        elif choice == '3':
            print("Exiting GitHub Personal Assistant. Goodbye!")
            break

        else:
            print("Invalid choice. Please enter 1, 2, or 3.")

if __name__ == "__main__":
    github_personal_assistant()
    
