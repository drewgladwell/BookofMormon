# BookofMormon
An analysis of the Book of Mormon and it's authors based on writing style, using NLP.

Step 1: Claude code helped clean up a CSV file of the Book of Mormon with seperate authors.

Note* Vocabulary richness is length-dependent. Shorter texts always score higher. Hence, authors like Jarom and Enos by default will have a much higher vocabulary richness since they wrote a considerably less amount of words than authors like Mormon or Nephi.

Term Frequency - Inverse Document Frequency

After coding the TF-IDF analysis, I decided to  use the expanded stopwords to highlight unique fingerprints per author. For example, since the Book of Mormon is a religious text, the words "Lord", "God", "People", etc are heavily repeated by each author. Since the purpose of the TF-IDF analysis is solely compare distinctions between authors, I decided to remove those words that appear repeatedly across all authors, and decided to include those in the word clouds analysis.

