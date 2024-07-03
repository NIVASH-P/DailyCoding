Remove all occurences of duplicates in a linked list

Program:

Map<Integer, Integer> mp = new HashMap<>();
        Node temp = head;
        List<Integer> v = new ArrayList<>();
        while (temp != null) {
            v.add(temp.data);
            mp.put(temp.data,mp.getOrDefault(temp.data,0)+1);
            temp = temp.next;
        }
        temp = head;
        Node pretemp = null;
        for (int i : v) {
            if (mp.get(i) == 1) {
                pretemp = temp;
                temp.data = i;
                temp = temp.next;
            }
        }
        if (pretemp != null) {
            pretemp.next = null;
        }
        return head;
