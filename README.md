# list-sort

// list<map>中集合元素排序 按时间  

  Collections.sort(list, new Comparator<Object>() {
    @Override
    public int compare(Object o1, Object o2) {
      Map<String, Object> map1 = (Map<String, Object>) o1;
      Map<String, Object> map2 = (Map<String, Object>) o2;
      SimpleDateFormat formatter2 = new SimpleDateFormat("yyyy-MM-dd");
      Date d2;
      Date d1;
      try {
        d1 = formatter2.parse((String) map1.get("createdate"));
        d2 = formatter2.parse((String) map2.get("createdate"));
        if (d1.getTime() > d2.getTime()) {
          return -1;
        } else {
          return 1;
        }
      } catch (ParseException e) {
        e.printStackTrace();
        return -1;
      }
    }
