```python
# python3 argparse_test.py --first apple --second banana
# python3 argparse_test.py -f apple -s banana
import argparse
parser = argparse.ArgumentParser()
parser.add_argument("-f", "--first", required=True)
parser.add_argument("-s", "--second", required=True)
args = parser.parse_args()
print("First arg is ", args.first) # args.f 
#apple
print("Second arg is ", sys.second) # args.s
#banana

# python3 argv_test.py apple banana
import sys
print("This is the name of the script: ", sys.argv[0])
#argv_test.py
print("First argv is ", sys.argv[1])
#apple
print("Second argv is ", sys.argv[2])
#banana
# print("Third arv is ", sys.arv[3])
# Error
```