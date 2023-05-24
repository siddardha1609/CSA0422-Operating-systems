#include <stdio.h>
#include <stdlib.h>
#define MAX 100

struct MemoryBlock {
  int start;
  int end;
  int size;
  int status;
};

int main() {
  int memorySize, numberOfProcesses;
  printf("Enter the size of memory: ");
  scanf("%d", &memorySize);
  printf("Enter the number of processes: ");
  scanf("%d", &numberOfProcesses);

  struct MemoryBlock blocks[MAX];
  for (int i = 0; i < MAX; i++) {
    blocks[i].status = 0;
  }

  blocks[0].start = 0;
  blocks[0].end = memorySize;
  blocks[0].size = memorySize;
  blocks[0].status = -1;

  int processSize[numberOfProcesses];
  printf("Enter the size of each process: \n");
  for (int i = 0; i < numberOfProcesses; i++) {
    scanf("%d", &processSize[i]);
  }

  for (int i = 0; i < numberOfProcesses; i++) {
    int processAssigned = 0;
    for (int j = 0; j < MAX; j++) {
      if (blocks[j].status == -1 || blocks[j].status == 0) {
        if (blocks[j].size >= processSize[i]) {
          int temp = blocks[j].start;
          blocks[j].start = temp + processSize[i];
          blocks[j].size = blocks[j].size - processSize[i];
          blocks[j].status = i + 1;
          processAssigned = 1;
          break;
        }
      }
    }
    if (processAssigned == 0) {
      printf("Process %d cannot be assigned to memory\n", i + 1);
    }
  }

  printf("Process No.\tStart\t\tEnd\t\tSize\t\tStatus\n");
  for (int i = 0; i < MAX; i++) {
    if (blocks[i].status != 0) {
      printf("%d\t\t%d\t\t%d\t\t%d\t\t%d\n", blocks[i].status, blocks[i].start - processSize[blocks[i].status - 1], blocks[i].start, processSize[blocks[i].status - 1], blocks[i].status);
    }
  }
  return 0;
}
