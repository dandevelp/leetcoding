# leetcoding
just some testing with leetcode, nothing special

---595
select name, population, area from World 
where (area >= 3000000 || population >= 25000000)

------------------
---1661
select a.machine_id, (round(avg(b.timestamp - a.timestamp),3)) processing_time from Activity a
join Activity b
on a.machine_id = b.machine_id
and a.process_id = b.process_id
and a.timestamp < b.timestamp
group by a.machine_id

----------------------
---- 151
//stack usage
class Solution {
public:
    string reverseWords(string s) {
        if(s.size() == 0) return s;
        stack<string> stack;
        string result;
        for(int i=0; i<s.size(); i++){
            string word;
            if(s[i]==' ') continue;
            while(i<s.size() && s[i]!=' '){
                word += s[i];
                i++;
            }
            stack.push(word);
        }
        while(!stack.empty()){
            result += stack.top();
            stack.pop();
            if(!stack.empty()) result += ' ';
        }
        return result;
    }
};


