# COMP122 Lecture Notes: October 28, 2024

## Announcements:
   1. Streetlight Effect

   1. Wisdom:
      * An old saying...
        - "Look before your leap!"
      * A new saying...
        - Review others questions, before your ask a redundant question?
          * You will get the answer to you problem faster!

   1. 04- graded
      - some students attempted branches 
        - their investment in themselves paid dividends

   1. What's changed:  The Prof did a `git pull`
      - diff {file1} {file2}
      - git diff {filename}
        * difference between working directory and HEAD

      - git diff {commit} [{filename}]
        * difference between working directory and the commit

      - git diff {commit} {commit}
        * difference between the two commits
          ```bash
          $ git pull
          remote: Enumerating objects: 1, done.
          remote: Counting objects: 100% (1/1), done.
          remote: Total 1 (delta 0), reused 1 (delta 0), pack-reused 0 (from 0)
          Unpacking objects: 100% (1/1), 210 bytes | 105.00 KiB/s, done.
          From github.com:COMP122/43-binary32-smf-steve
             3d244fb..70b4226  main       -> origin/main
          Updating 3d244fb..70b4226
          Fast-forward
          README.md | 125 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++
          1 file changed, 125 insertions(+)
          create mode 100644 mips/binary32.s
          $ git diff 3d244fb 70b4226 README.md
          ```


## Today's Agenda:

  1. Lecture
     1. Practicum
        - int bit2int()
        - int binary2int()
        - Manual Testing:
          - echo 0 | java_subroutine bit2int

     1. switch/case statement

     1. Practicum
        - int glyph2int()
        - int nextInt(int radix);

  1. Lab: 
     1. Cleanup
     1. Time to work on practicum

## Questions from Last Lecture/Lab, etc.:
   * M/W
     - Subroutine in mips... 
     - Is the Prof's expectations to high?


   * T/R

## Any Review?

---
# Today's Lecture Material

  1. Lecture
     * Have you read this?
       - reference/TAC_transformation.md

     1. Practicums: 
        * Versions
          - the Prof's version
            ```bash
            cd ~/classes/comp122/practicums
            git clone git@github.com:COMP122/code_10_28.git 
            ```
          - my (student's) version
            ```bash
            cd ~/classes/comp122/practicums
            mkdir code_10_28_{github_account}
            ```
        * Input:
          ```
          mips.read_c();
          c = mips.retval();     # -1 is returned if nothing to read
          ```

        * int bit2int();
          - reads an ASCII char
          - returns 
            * 0 if '0'
            * 1 if '1'
            * -1 otherwise

        * int binary2int();
          - returns number

          ```psudeo 
          number = number * 2 + git_bit()
          ```

     1. Java switch/case statement
        - reference/TAC_transformation/switch.png
        - Example
          ```java
           switch(expression) {
                   
             case x:
                 ; // code block
                 break; 
                   
             case y:
                 ; // code block
                 break;

             case z:
                 ; // code block
                 break;
                   
             default:
                 ;    // code block
                 break;
            }
          ```

        - Java if-then-else equivalence
          * see your notes

        - Java TAC transformation
          - blocks:
            * init
            * body
            * done
            * each "case"
          - mips.next("{value}")
          - mips.merge("{value}") 
          - Example:
            ```java tac
            init:  ;
                   {var} = expression;
            split: switch( {var} ) {
                   
                      case x:
                          mips.next(y);
                          ; // code block
                          break split; 
                          mips.merge(y);
                            
                      case y:
                          mips.next("default");
                          ; // code block
                          break;
                          mips.merge("default");

                      default:
                          ;    // code block
                          break split;
                     }
            done:  ; 
            ```



     1. C Switch Statement
        ```c
        switch (input) {
          case '0'...'9' :   digit = digit - '0';
                             break;

          case 'A'...'F' :   digit = digit - 'A' 
                             digit = digit + 10;
                             break;

          case 'a'...'f' :   digit = digit - 'a' 
                             digit = digit + 10;
                             break;
          default:           digit = -1;
        }
        if (digit > (radix - 1)) {
          digit = -1;
        }
        return digit;
        ```

        - Java Equivalent Statement



        - C if-then-else equivalence 
          * in_range(value, '0', '9')

     1. Practicum
        - int glyph2int(int radix);
          - reads an ASCII char
          - returns 
            * 0 if '0'
            * 1 if '1'
            * etc.
            * -1 otherwise
        - int nextInt(int radix);
          - returns number
          ```psudeo 
          number = number * radix + glyph2int(radix)
          ```
  1. Lab: 
     1. Cleanup
     1. Time to work on practicum
        - This code is part of your next assignment!

 
# Today's Lab Material


---
## Resources

* reference/TAC_transformation.md
* reference/TAC2mips.md


---
<!-- This section for student's to place their own notes. -->
<!-- This section will not be updated by the Professor.   -->

## Notes  


