
1. Create Managed Kubernetes cluster in your cloud provider of choice - Do this however you want (AWS/EKS, Azure/AKS, GCP/GKE - Lots of free 'credit' options out there.)
    - (Note: A node with 4cpu and 8 gigs of ram should be fine to run the Sysdig agent on with the below voting app)
    - If you're building in the cloud, and you're new to the cloud, learn about security and billing alerts!
    - Turn off or scale down your cluster when you're not using it, but **don't destroy it!**
4. Connect your cloud account to Sysdig using the onboarding Wizard.
5. Install the Sysdig Agent(s) to your Kubernetes cluster, once again we suggest using the onboarding Wizard.
6. Install the classic *voting app* into your K8s cluster (https://github.com/dockersamples/example-voting-app)
    - Clone the repo to your github
    - Expose the app so you can browse to the UI and see it working
7. Get Creative and build some stuff in Sysdig.
    - In Sysdig Secure:
        - Scan the images being used for the Voting App, what do the results mean? Which one has the most Risk? Why?
        - Bonus points if you setup a Github action to build the vote, worker and result containers and scan them with our cli scanner
        - Integrate Sysdig IaC with the voting app in your github repo.
        - Compliance? Setup a Zone for your App & repo. Configure a benchmark to run. Submit a PR to the voting app repo from Sysdig compliance 
        - Enable Runtime Policies, generate some events. Be creative with the events you create and then. Show us how you did it and why you think the activity maybe suspicious?
        - Activity audit! Why's that valuable?
    - In Sysdig Monitor:
        - Advisor, what is the usage of your cluster vs the requests and limits? What other interesting information can you find?
        - Build a PromQL query using the query builder in the explore section of Sysdig Monitor using metrics from the Voting App (bonus points if you use StatsD metrics in a PromQL query)
        - Build a dashboard with your query + static metrics from Sysdig that relate multiple things together
        - Add views to the dashboard that might be interesting to a user
