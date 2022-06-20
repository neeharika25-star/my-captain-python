def scraper():
    for i in range(1,6): # fetching reviews from five pages
        pagewise_reviews = [] 
        query_parameter = "?page="+str(i)
	url = base_url + query_parameter
	response = requests.get(url)
	soup = bs(response.content, 'html.parser') 
	rev_div = soup.findAll("div",attrs={"class","rvw-bd"}) 

    for j in range(len(rev_div)):
    # finding all the p tags to fetch only the review text
        pagewise_reviews.append(rev_div[j].find("p").text)

    for k in range(len(pagewise_reviews)):
        all_pages_reviews.append(pagewise_reviews[k]) 
        return all_pages_reviews

# Driver code
reviews = scraper()
i = range(1, len(reviews)+1)
reviews_df = pd.DataFrame({'review':reviews}, index=i)
reviews_df.to_csv('reviews.txt', sep='t')
