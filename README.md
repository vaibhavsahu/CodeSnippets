# CodeSnippets
Utility Code snippets for Java

1. Sort the Map based on Keys
    //sort the map by keys
    Map<String, List<Vote>> sortedMap = map.entrySet().stream()
                .sorted(Map.Entry.comparingByKey())
                .collect(Collectors.toMap(Map.Entry::getKey, Map.Entry::getValue,
                        (oldValue, newValue) -> oldValue, LinkedHashMap::new));
  
2. Remove duplicate((if two objects have same matching property) objects from a list using a property
    public class Vote {
        private String preference;
        private String option;
        private int count;
    }
    Set<String> set = new HashSet<>();
    voteList.removeIf( vote -> !set.add(vote.getOption())); //votes with same option will be removed
  
3. Group the list of objects based on some property  
    public class Vote {
        private String preference;
        private String option;
        private int count;
    }
    List<Vote> votes = new ArrayList<>();
    
    //grouping the objects using preference property
    Map<String, List<Vote>> map = votes.stream().collect(Collectors.groupingBy(Vote::getPreference));
  
4. Compare if two lists are equal
    Objects.equal(list1, list2); returns true if lists are equal else false
    
    
