<h1 align="center"> Things to do. </h1>

# Client-server flow (Page 4)
1. [x] Listen for client connection.

2. [x] Receive first and second arrays into `INPUT_STRING` and convert them to
   integer arrays `FIRST_ARRAY` and `SECOND_ARRAY` repectively.

3. [x] Spawn N threads where:
    - [x] N is the number of integers in one of the arrays.
    - [x] Threads are stored in `THREAD_ARRAY`.
    - [x] Every thread is assigned to **only one index address**
    - [x] Carries are written to `CARRY_ARRAY`
    - [x] Results are written to `RESULT_ARRAY`

4. [x] Join N threads.

5. [x] Add the carries to their correct `RESULT_ARRAY` index.
    - [x] After addition, propagate necessary carries. (page 5, paragraph 3)
    - [x] If there is a carry in the first element, shift, and set the first
      element as carry

6. [x] Transform `RESULT_ARRAY` into string.
    - [x] ⚠️  **DO NOT USE `INPUT_STRING`: This is a potential buffer overrun.**
    - [x] Use a buffer size `#define RESULT_STRING_SIZE 512`
    - [x] Use a buffer `RESULT_STRING`

7. [x] Close the connection and go back to the first step.

# Requirements (Page 2 and 5)
- [x] Write comments.

- [ ] Send error messages based on:
    - [ ] Whether there is a **negative number** in the list
    - [ ] Whether the **number of integers** differ by two arrays.
    - [ ] Whether the **numbers are in range** [0, 999]
    - [ ] Whether there is a **non integer and space** character.
    - [ ] Whether the input **string length** was over the limit.
        - This is a requirement in the spec. We should *try and see* if we can
          detect this with telnet. If we can or can't detect this, we should
          explain it in the comments.

- [x] Store global variables (these are required by the spec)
    - [x] `INPUT_STRING`, `FIRST_ARRAY`, `SECOND_ARRAY`, `CARRY_ARRAY`, `RESULT_ARRAY`,
    - [x] `DATA_SIZE`, `PORT_NUMBER`
    - [x] `THREAD_ARRAY`
